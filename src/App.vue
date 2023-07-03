<template>
  <div id="app">
    <Galeria/>
  </div>
</template>

<script>
import Galeria from '@/components/Galeria.vue';

export default {
  name: 'App',
  components: {
    Galeria
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
