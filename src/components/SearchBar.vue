<template>
  <div class="search-bar">
    <form action="javascript:void(0);">
    <label for="queryInput">SearchBar:</label><input id="queryInput" placeholder="SearchBar" v-on:change="onChange"/>
    <button>Search</button>
  </form>
  </div>
</template>

<script>
export default {
  name: 'SearchBar',
  props: {
    msg: String
  },
  // data: function() {
  //   query:""
  // },
  methods:
  {
    onChange: function(event) {
      // this.query = event.target.value;
      // console.log(this.query);
      this.$emit('searchTermChange', event.target.value);
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
