<template>
  <Navbar brand-name="Countries API" />
  <router-view />
  <Search @search-results="showResults"></Search>
  <SearchResults v-if="searched" :countries="countries"></SearchResults>
</template>

<script>
import Navbar from '../src/components/Navbar/index.vue';

export default {
  components: {
    Navbar
  },
}
</script>
