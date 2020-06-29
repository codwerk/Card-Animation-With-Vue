<template lang="pug">
  #app
    Card(:card="card" v-for="(card, index) in cards" :key="index")
</template>

<script>
import Card from './components/Card'

export default {
  name: 'App',
  components: {
    Card
  },
  data () {
    return {
       cards: [
         {
           title: "I - Lorem ipsum dolor sit amet consectetur",
           description: 'Lorem ipsum dolor, sit amet consectetur adipisicing elit. Excepturi alias fuga soluta labore ducimus voluptatem esse mollitia similique ea sed!',
           img: '/appstore_01.jpg',
           open: false
         },
         {
           title: "II - Lorem ipsum dolor sit amet consectetur",
           description: 'Lorem ipsum dolor, sit amet consectetur adipisicing elit. Excepturi alias fuga soluta labore ducimus voluptatem esse mollitia similique ea sed!',
           img: '/appstore_02.jpg',
           open: false
         },
         {
           title: "III - Lorem ipsum dolor sit amet consectetur",
           description: 'Lorem ipsum dolor, sit amet consectetur adipisicing elit. Excepturi alias fuga soluta labore ducimus voluptatem esse mollitia similique ea sed!',
           img: '/appstore_03.jpg',
           open: false
         },
         {
           title: "IV - Lorem ipsum dolor sit amet consectetur",
           description: 'Lorem ipsum dolor, sit amet consectetur adipisicing elit. Excepturi alias fuga soluta labore ducimus voluptatem esse mollitia similique ea sed!',
           img: '/appstore_04.jpg',
           open: false
         }
       ]
    }
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
