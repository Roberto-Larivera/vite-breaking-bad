<script>
import axios from 'axios';
import { store } from './store.js';
import AppHeader from './components/Header/AppHeader.vue';
import AppMain from './components/Main/AppMain.vue';
import AppFooter from './components/Footer/AppFooter.vue';
export default{
  name: 'App',
  components:{
    AppHeader,
    AppMain,
    AppFooter,
  },
  data(){
    return{
      store,
    }
  },
  created() {
    axios
      .get('https://db.ygoprodeck.com/api/v7/cardinfo.php')
      .then((response)=>{
        console.log(response.data.data.slice(0,10));
        this.store.listCard = (response.data.data.slice(0,10));
        console.log('listCard',this.store.listCard)
      });
  },
}
</script>

<template>
  <div>
    <AppHeader/>
    <AppMain/>
    <!-- <AppFooter/> -->
  </div>
</template>

<style lang="scss">
@import './style/main.scss';

body{
  background-color: #2E3A46;
}

</style>
