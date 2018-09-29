<template>
  <div id="app">
    <nav class="navbar navbar-light bg-light">
      <a class="navbar-brand">Mercadolibre Search</a>
      <form class="form-inline">
        <input class="form-control mr-sm-2" type="search" placeholder="Search" aria-label="Search" v-model="value">
        <button class="btn btn-outline-success my-2 my-sm-0" type="submit" @click="getValue">Search</button>
      </form>
    </nav>
    <ItemsList :object= 'info'/>
  
  </div>
</template>



<script>
import ItemsList from './components/items_list.vue'
import Axios from 'axios'

export default {
  name: 'app',
  data(){
    return{
      info: [],
      value: "xiaomi"

    }
  },
  components: {
    SearchBar,
    ItemsList
  },
   mounted () {
    Axios.get(`https://api.mercadolibre.com/sites/MCO/search?q=${this.value}&limit=5`)
      .then(response => (this.info = response.data.results))
  },
  methods:{
    getValue(e) {
        e.preventDefault();
        Axios.get(`https://api.mercadolibre.com/sites/MCO/search?q=${this.value}&limit=5`)
      .then(response => (this.info = response.data.results))

     }
  }

  
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 0px;
}
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
