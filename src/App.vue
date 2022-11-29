<template>
  <div>
    <img alt="Vue logo" src="./assets/logo.png">
    <SearchBar v-on:searchTermChange="handleSearchTermChange"></SearchBar>
  </div>
</template>

<script>
import SearchBar from './components/SearchBar.vue'

export default {
  name: 'App',
  components: {
    SearchBar
  },
  methods: {
    handleSearchTermChange: function(newTerm) {
      console.log(newTerm);
    }
  },
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
