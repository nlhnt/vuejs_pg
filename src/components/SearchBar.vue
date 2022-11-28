<template>
  <div class="search-bar">
    SearchBar: <input placeholder="SearchBar" v-on:change="onChange"/>
  </div>
</template>

<script>
export default {
  name: 'SearchBar',
  props: {
    msg: String
  },
  methods:
  {
    onChange: function(event) {
      console.log(event.target.value);
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
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
}
</style>
