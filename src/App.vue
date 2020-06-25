<template lang="pug">
  <div id="app">
    Card
  </div>
</template>

<script>
import Card from './components/Card'

export default {
  name: 'App',
  components: {
    Card
  }
}
</script>

<style>

@import url('./assets/scss/index.scss');

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
</style>
