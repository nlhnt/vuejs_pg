<template>
  <div>
    <img alt="Vue logo" src="./assets/logo.png">
    <SearchBar v-on:searchTermChange="handleSearchTermChange"></SearchBar>
  </div>
</template>

<script>
import axios from 'axios';
import SearchBar from './components/SearchBar.vue';
const API_KEY = 'AIzaSyBslo0K2TH7YLH7OQs5rgMxUmsA8Dj26FA';
// just to cut the error of not being used
// console.log(API_KEY.split('')[0])

export default {
  name: 'App',
  components: {
    SearchBar
  },
  methods: {
    handleSearchTermChange: function(newTerm) {
      console.log(newTerm);
      console.log(typeof(newTerm));
      axios.get('https://www.googleapis.com/youtube/v3/search', {
        params: {
          key: API_KEY,
          type: 'video',
          parent: 'snippet',
          q: newTerm
        }
      }).then(response => console.log(response));
      // console.log(search_res);
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
