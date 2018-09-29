<template>
    <div  class="list-group">
        <ul class="list-group-item">
            <li  ><Items :key="obj" v-for="obj in object" :title="obj.title" :price="obj.price" :imgUrl="obj.thumbnail"></Items> </li>
        </ul>
    </div>
</template>


<script>
import Items from './items.vue'
export default {
name: 'ItemsList',
props: {
    object: []

  },
  components: {
    Items
  },
}
</script>

<style>
    .centralizar{
        display: block;
    margin-left: auto;
    margin-right: auto
    }
</style>