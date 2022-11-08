<template>
  <MainCard/>
</template>

<script>
import MainCard from './components/MainCard.vue'
export default {
  name: 'App',
  components: {
    MainCard,
  }
}
</script>

<style>
@import url(https://fonts.googleapis.com/css?family=Anonymous+Pro);
@import url('https://fonts.googleapis.com/css?family=Raleway:300,400');

body {
  margin: 0;
}
#app {
  
  font-family:'Anonymous Pro', monospace;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #ffffff;
  background-color: #7fb3bb;
  border: 33px solid #7fb3bb;
  min-height: 105vh;
}
</style>
