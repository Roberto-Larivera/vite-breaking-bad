<script>
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
  background-color: $color_primary;
}

</style>
