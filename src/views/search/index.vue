<template>
    <div class="row h-100 w-100">
        <h1>API full name</h1>
    </div>
    <router-view />
    <Search @search-results="showResults"></Search>
    <SearchResults v-if="searched" :countries="countries"></SearchResults>
    
</template>

<script>
import Search from '/src/components/countries/Search.vue';
import SearchResults from '/src/components/countries/SearchResults.vue';



export default({
    components:{
        Search,
        SearchResults
    },
    data() {
    return {
      searched: false,
      countries: []
    }
  },
  methods: {
    showResults(countries) {
      this.searched = true
      this.countries = countries
    }
  }
});
</script>