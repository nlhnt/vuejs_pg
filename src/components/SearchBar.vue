<template>
  <div class="search-bar row align-items-center mx-2">
    <form action="javascript:void(0);">
    <label class="col" for="queryInput">SearchBar: </label><input id="queryInput" placeholder="SearchBar" v-on:change="onChange" class="col-8"/>
    <button type="button" class="btn btn-info col">Search</button>
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
/* input {
  width: 75%
}
button {
  width: 15%
} */
</style>
