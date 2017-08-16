<template>
  <div id="app">
    <img src="//placehold.it/500x10" alt="">
    <button @click="resetAll">Reset All</button>
    <div class="container">
      <div class="row">
        <div class="col-sm-6" v-for="banana in opponents">
          <slap :target="banana"></slap>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  import Slap from './components/Slap'

  export default {
    name: 'app',
    data() {
      return {
        opponents: [
          { name: 'Mark', health: 100, img: 'https://ca.slack-edge.com/T1GGQN1RU-U2APRMARY-1de87c8e201a-48' },
          { name: 'Jim', health: 100, img: 'https://cdn.shopify.com/s/files/1/0042/9942/products/print_jimpainting02.jpg?v=1448096635' },
          { name: 'Fred', health: 100, img: 'https://cdn.shopify.com/s/files/1/0042/9942/products/print_jimpainting02.jpg?v=1448096635' }
        ]
      }
    },
    methods:{
      resetAll(){
        for(var i = 0; i < this.opponents.length; i++){
          var opponent = this.opponents[i]
          opponent.health = 100
        }
      }
    },
    components: {
      Slap
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




