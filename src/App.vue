<script>
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

    }
  }
}
</script>

<template>
  <div>
    <AppHeader/>
    <AppMain/>
    <AppFooter/>
  </div>
</template>

<style lang="scss">
@import './style/main.scss';

</style>
