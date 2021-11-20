<template>
<h1> Please add the URL </h1>
  <form>
    <input v-model="URL" type="text">
    <input @click.prevent="getBuiltWithData" type="submit">
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
      URL: '',
    }
  },
  methods: {
    getWhoIsData() {
      axios.get(this.formattedWhoIsURL).then((data) => console.log(data))
    },
    getBuiltWithData() {
      axios.get(this.formattedBuiltWithURL).then((data) => console.log(data))
    }
  },
  computed: {
    formattedWhoIsURL() {
      return `https://api.domaintools.com/v2/domain-search/?query=[${this.URL}]`
    },
    formattedBuiltWithURL() {
      return `https://api.builtwith.com/free1/api.[xml|json]?KEY=0c73f8cb-b699-404e-93f4-3894486431ed&LOOKUP=${this.URL}`
    }

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
