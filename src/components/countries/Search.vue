<template>
  <div class="search-container">
    <input v-model="query" type="text" placeholder="Buscar país" class="search-input">
    <button @click="search()" class="search-button">Buscar</button>
  </div>
</template>

<style>
.search-container {
  display: flex;
  justify-content: center;
  align-items: center;
  margin-top: 50px;
}

.search-input {
  height: 40px;
  width: 500px;
  font-size: 18px;
  border: 2px solid #ced4da;
  border-radius: 5px;
  padding: 5px 10px;
}

.search-button {
  height: 40px;
  font-size: 18px;
  color: #fff;
  background-color: #007bff;
  border: 2px solid #007bff;
  border-radius: 5px;
  padding: 5px 20px;
  margin-left: 10px;
}

.search-button:hover {
  background-color: #0069d9;
  border-color: #0062cc;
}

.search-input:focus {
  outline: none;
  border-color: #007bff;
  box-shadow: 0 0 0 0.2rem rgba(0, 123, 255, 0.25);
}

</style>

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