<template>
  <div class="row video-list align-items-start">
    <p>VideoList</p>
    <p>Num of videos: {{ videos.length }}</p>
    <ul class="list-group">
      <VideoListItem
        v-for="video in videos"
        :key="video.etag"
        v-bind:video="video"
        v-on:videoSelectEvent="handleVideoSelectEvent"
      ></VideoListItem>
    </ul>
  </div>
</template>

<script>
import VideoListItem from './VideoListItem.vue'

export default {
  name: 'VideoList',
  components: {
    VideoListItem
  },
  // props: ['videos']
  props: {
    videos: Array
  },
  // data: function() {
  //   query:""
  // },
  methods:
  {
    handleVideoSelectEvent: function(selectedVideo) {
      this.$emit('videoSelectEvent', selectedVideo)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
/* h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
} */
</style>
