<template>
    <ul>
      <li class="texto" v-for="country in countries" :key="country.name.common">{{ country.name.common }}</li>
      <li v-for="country in countries" :key="country.name.official">{{ country.name.official}}</li>
      <!--<li v-for="country in countries" :key="country.nativeName.nvl">{{ country.nativeName.nvl }}</li>-->
    </ul>
  </template>

  <style>
   .texto { 
   width: 100%;
}
th, td {
   width: 25%;
   text-align: left;
}




  </style>

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
  