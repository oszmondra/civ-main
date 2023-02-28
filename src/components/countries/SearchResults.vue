<template>
    <ul>
      <li v-for="country in countries" :key="country.name.common">{{ country.name.common }}</li>
      <li v-for="contry in countries" :key="country.nativeName.nvl">{{country.name.common }}</li>
    </ul>
  </template>
  
  <script>
  export default {
    name: 'SearchResults',
    props: {
      countries: {
        type: Array,
        required: true
      }
    }
  }
  </script>
  