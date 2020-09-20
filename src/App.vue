<template>

  
  <!--<Welcome msg=""/> -->
  <Header/>
  <Body />
  <Vue/>
  <VueCarousel/>
  <Footer/>
  
</template>

<script>
//import Welcome from './components/Welcome.vue'
import Header from './components/Header.vue'
import Footer from './components/Footer.vue'
import Body from './components/Body.vue'
import Vue from 'vue'
import VueCarousel from 'vue-carousel'


export default {
  name: 'App',
  components: {
    Header,Footer,Body,VueCarousel,Vue
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}


@import "../src/assets/css/nutrStyle.css";




</style>
