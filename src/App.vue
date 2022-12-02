<template>
  <div class="container">
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <SearchBar v-on:searchTermChange="handleSearchTermChange"></SearchBar>
    <VideoList v-bind:videos="videos"></VideoList>
    <!-- <p>Number of videos: {{ videos.length }}</p> -->
  </div>
</template>

<script>
import axios from 'axios';
import SearchBar from './components/SearchBar.vue';
import VideoList from './components/VideoList.vue'
const API_KEY = 'AIzaSyBslo0K2TH7YLH7OQs5rgMxUmsA8Dj26FA';
// just to cut the error of not being used
// console.log(API_KEY.split('')[0])

export default {
  name: 'App',
  components: {
    SearchBar,
    VideoList
  },
  data: function(){ // data() {}
    return {
      videos: []
    };
  },
  methods: {
    handleSearchTermChange: function(newTerm) {
      console.log(newTerm);
      console.log(typeof(newTerm));
      // https://developers.google.com/youtube/v3/docs/videos/list#request
      axios.get('https://www.googleapis.com/youtube/v3/search', {
        params: {
          key: API_KEY,
          type: 'video',
          part: 'snippet',
          q: newTerm
        }
      }).then(response => {
        // curly braces only encapsulate and make the formating easier in here
        this.videos = response.data.items;
      });
      // response => console.log(response)
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
