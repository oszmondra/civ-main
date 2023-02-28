<template>
    <div>
      <input v-model="query" type="text" placeholder="Buscar país">
      <button @click="search()">Buscar</button>
    </div>
  </template>
  
  <script>
  import axios from 'axios'
  
  export default {
    name: 'Search',
    data() {
      return {
        query: ''
      }
    },
    methods: {
      search() {
        axios.get(`https://restcountries.com/v3.1/name/${this.query}?fullText=true`)
          .then(response => {
            this.$emit('search-results', response.data)
          })
          .catch(error => {
            console.log(error)
          })
      }
    }
  }
  </script>
  