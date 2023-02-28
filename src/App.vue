<template>
  <Navbar brand-name="Countries API" />
  <router-view />
  <Search @search-results="showResults"></Search>
  <SearchResults v-if="searched" :countries="countries"></SearchResults>
</template>

<script>
import Navbar from '../src/components/Navbar/index.vue';
import Search from '../src/components/countries/Search.vue'
import SearchResults from '../src/components/countries/SearchResults.vue'

export default {
  components: {
    Navbar,
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
}
</script>
