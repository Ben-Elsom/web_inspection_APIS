<template>
<h1> Please add the URL </h1>
  <form>
    <input v-model="url"  type="text">
    <input @click.prevent="getData" type="submit">
  </form> 
  <img alt="Vue logo" src="./assets/logo.png">
</template>

<script>

// import * as Vue from 'vue' // in Vue 3
 import axios from 'axios'
// import VueAxios from 'vue-axios'

export default {
  name: 'App',
  data() {
    return {
    }
  },
  methods: {
    log(text) {
      console.log(text);
    },
    getData() {
      axios.get('https://api.coindesk.com/v1/bpi/currentprice.json').then((data) => console.log(data))
    }

  },
  computed: {

  },
  components: {
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
