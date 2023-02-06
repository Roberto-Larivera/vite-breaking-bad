<script>
import { store } from '../../store.js';
import SingleCard from './SingleCard.vue'
export default {
  name: 'AppMain',
  components:{
    SingleCard,
  },
  data() {
    return {
      store,
    }
  }

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
      <div class="row row-cols-1">
        <div class="col">

          <div>
            found character
          </div>
        </div>
        <div class="col">

          <div class="row row-cols-5">
            list card

            <div class="col">

              <SingleCard 
              :infoName="store.listCard[0].name"
              
              />

            </div>
            <!-- :imgSrc="store.listCard[0][card_images[0]].image_url"
            
            :infoType="store.listCard[0].type"
              :infoArcheType="store.listCard[0].archetype"
              :infoDesc="store.listCard[0].desc" -->
          </div>
        </div>

      </div>

    </div> <!--fine container-->
  </main>
</template>

<style lang="scss" scoped>

</style>
