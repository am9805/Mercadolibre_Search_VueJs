<template>
<nav class="navbar navbar-light bg-light">
  <a class="navbar-brand">Mercadolibre Search</a>
  <form class="form-inline">
    <input class="form-control mr-sm-2" type="search" placeholder="Search" aria-label="Search">
    <button class="btn btn-outline-success my-2 my-sm-0" type="submit">Search</button>
  </form>
</nav>
</template>

<script>
export default {
  name: 'SearchBar',
  props: {
    msg: String
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
.bg-light {
    background-color :#ffe600!important;
}
.btn-outline-success {
    color: #2d3277;
    background-color: transparent;
    background-image: none;
    border-color: #2d3277;
}
</style>
