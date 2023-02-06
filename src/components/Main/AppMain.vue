<script>
import { store } from '../../store.js';
import SingleCard from './SingleCard.vue'
import FoundCard from './FoundCard.vue'
import SectionCard from './SectionCard.vue'
export default {
  name: 'AppMain',
  components: {
    SingleCard,
    FoundCard,
    SectionCard,
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
      <div class="row justify-content-center">
        <div class="col-auto p-4">
          <SectionCard />
        </div>
      </div>

      <!--section principal-->
      <div class="section_principal row row-cols-1 p-5">
        <div class="principal-found col p-3 mb-3 d-flex justify-content-center align-items-center">
          <FoundCard :myNumber="store.listCard.length"/>
        </div>
        <div class="col">

          <div class="list_cards row row-cols-1 row-cols-sm-1 row-cols-md-3 row-cols-lg-4 row-cols-xl-5 g-3" v-if="store.listCard.length == 10">
           <template v-for="element in store.listCard">
            <div class="col d-flex align-items-stretch ">
              <SingleCard 
                :imgSrc="element.card_images[0].image_url" 
                :infoName="element.name"
                :infoType="element.type"
                :infoArcheType="element.archetype"
                :infoDesc="element.desc"
                />
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
  .principal-found{
    background-color: $color_primary;
    border-radius: 20px;
    color: whitesmoke;
  }
}
</style>
