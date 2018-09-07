<template>
  <div>
    <Snowman />
  </div>
</template>

<script>
import Snowman from './components/Snowman.vue'

export default {
  name: 'App',
  components: {
    Snowman
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
