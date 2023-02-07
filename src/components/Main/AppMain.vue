<script>
import axios from 'axios';
import { store } from '../../store.js';
import SingleCard from './SingleCard.vue'
import FoundCard from './FoundCard.vue'
import SectionCard from './SectionCard.vue'
import LoadingSpinner from './LoadingSpinner.vue'
export default {
  name: 'AppMain',
  components: {
    SingleCard,
    FoundCard,
    SectionCard,
    LoadingSpinner,
  },
  data() {
    return {
      store,
    }
  },
  methods: {
    // LIST REQUEST CARD
    getCharacters() {
      this.store.loadingTime = true
      //console.log(this.store.loadingTime)
      axios
        .get('https://db.ygoprodeck.com/api/v7/cardinfo.php')
        .then((response) => {
          //console.log(response.data.data.slice(0, 10));
          this.store.listCard = (response.data.data.slice(0, 30));
          //console.log('listCard', this.store.listCard)
          this.store.loadingTime = false
        })
        .catch((error) => {
          console.log('error', error)
          this.store.listCard = []
          this.store.loadingTime = false
        });

      //console.log(this.store.loadingTime)

    },

    // LIST REQUEST FILTRATA
    getFilterCharacters() {
      this.store.loadingTime = true
      //console.log(this.store.loadingTime)
      axios
        .get('https://db.ygoprodeck.com/api/v7/cardinfo.php', {
          params: {
            archetype: store.selectValue
          }
        })
        .then((response) => {
          //console.log(response.data.data.slice(0, 10));
          this.store.listCard = (response.data.data.slice(0, 30));
          //console.log('listCard', this.store.listCard)
          this.store.loadingTime = false
        })
        .catch((error) => {
          console.log('error', error)
          this.store.listCard = []
          this.store.loadingTime = false
          this.getCharacters()
        });

      //console.log(this.store.loadingTime)

    },

    // LIST REQUEST ARCHETYPE
    getArchetype() {
      axios
        .get('https://db.ygoprodeck.com/api/v7/archetypes.php?')
        .then((response) => {
          //console.log(response.data);
          this.store.listArchetype = (response.data);
          console.log('listArchetype', this.store.listArchetype)
        });
    },

  },
  created() {
    this.getCharacters()
    this.getArchetype()
  },
  computed: {

  }

}
</script>

<template>
  <main>
    <div class="container">

      <!--select category-->
      <div class="row justify-content-center">
        <div class="col-auto p-4">
          <SectionCard @search="getFilterCharacters()" />
        </div>
      </div>

      <!--section principal-->
      <div class="section_principal row row-cols-1 p-5">
        <div class="principal-found col p-3 mb-3 d-flex justify-content-center align-items-center">
          <FoundCard :myNumber="store.listCard.length" />
        </div>
        <div class="col">

          <div v-if="store.loadingTime" class="h-100">
            <LoadingSpinner />
          </div>

          <div class="list_cards row row-cols-1 row-cols-sm-1 row-cols-md-3 row-cols-lg-4 row-cols-xl-5 g-3" v-else>
            <!-- v-if="store.listCard.length == 10"-->
            <template v-for="element in store.listCard">
              <div class="col d-flex align-items-stretch ">
                <!-- :imgSrc="element.card_images[0].image_url"  -->
                <SingleCard :infoName="element.name" :infoType="element.type" :infoArcheType="element.archetype"
                  :infoDesc="element.desc" />
              </div>
            </template>
          </div>

        </div>

      </div>

    </div> <!--fine container-->
  </main>
</template>

<style lang="scss" scoped>
.section_principal {
  background-color: whitesmoke;
  min-height: 500px;

  .principal-found {
    background-color: $color_primary;
    border-radius: 20px;
    color: whitesmoke;
  }
}
</style>
