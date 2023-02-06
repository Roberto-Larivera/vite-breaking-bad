<script>
import { store } from '../../store.js';
import SingleCard from './SingleCard.vue'
export default {
  name: 'AppMain',
  components: {
    SingleCard,
  },
  data() {
    return {
      store,
    }
  },

}
</script>

<template>
  <main>
    <div class="container">

      <!--select category-->
      <div class="row row">
        <div class="col">
          section category
        </div>
      </div>

      <!--section principal-->
      <div class="section_principal row row-cols-1 p-5">
        <div class="col">

          <div>
            found character
          </div>
        </div>
        <div class="col">

          <div class="list_cards row row-cols-1 row-cols-sm-1 row-cols-md-3 row-cols-lg-4 row-cols-xl-5 g-5" v-if="store.listCard.length == 10">
           <template v-for="element in store.listCard">
            <div class="col">
              <SingleCard 
                :imgSrc="element.card_images[0].image_url" 
                :infoName="element.name"
                :infoType="element.type"
                :infoArcheType="element.archetype"
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
  .list_cards{
    .col{
      min-height: 150px;
    }
  }
}
</style>
