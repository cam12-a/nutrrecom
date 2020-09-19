<template>
  
  <!--<Welcome msg=""/> -->
  <Header />
</template>

<script>
//import Welcome from './components/Welcome.vue'
import Header from './components/Header.vue'

export default {
  name: 'App',
  components: {
    Header
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

@import "../src/assets/css/style.css";
@import "../src/assets/css/style.scss";




</style>
