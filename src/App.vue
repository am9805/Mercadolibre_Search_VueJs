<template>
  <div id="app">
    <SearchBar/>
    <ItemsList :object= 'info'/>
  
  </div>
</template>

<script>
import SearchBar from './components/search_bar.vue'
import ItemsList from './components/items_list.vue'
import Axios from 'axios'

export default {
  name: 'app',
  data(){
    return{
      info: []

    }
  },
  components: {
    SearchBar,
    ItemsList
  },
   mounted () {
    Axios.get('https://api.mercadolibre.com/sites/MCO/search?q=iphone&limit=5')
      .then(response => (this.info = response.data.results))
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
</style>
