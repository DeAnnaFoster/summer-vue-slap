<template>
  <div class="hello">
    <h1 :class="{red: target.health <= 25, green: target.health > 80, orange: target.health <= 80 && target.health > 25}">{{ target.name }} {{target.health}}</h1>
    <button class="btn btn-primary" v-if="target.health > 0" @click="slap">SLAP {{target.name}}</button>
    <button class="btn btn-danger" @click="curbStomp" :disabled="target.health <= 0">KILL {{ target.name }}</button>
    <button @click="reset">RESET</button>
    <div>
      <img :src="target.img">
    </div>
  </div>
</template>

<script>
  export default {
    name: 'hello',
    props: ['target'],
    data() {
      return {}
    },
    methods: {
      slap() {
        this.target.health -= 1
        this.checkHealth()
      },
      curbStomp() {
        this.target.health -= 105
        this.checkHealth()
      },
      checkHealth() {
        if (this.target.health < 0) {
          this.target.health = 0
        }
      },
      reset() {
        this.target.health = 100
      }
    }

  }

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .red {
    color: red;
  }

  .green {
    color: green;
  }

  .orange {
    color: orange;
  }

  img{
    height: 100px;
    width: 100px;
  }
</style>