<template>
    <div class="card centralizar" style="width: 18rem;">
        <img class="card-img-top" :src="imgUrl" alt="Card image cap">
        <div class="card-body">
            <h5 class="card-title">{{title}}</h5>
            <p class="card-text">El precio es: ${{price}}</p>
        </div>
    </div>
</template>
<script>
export default {
  name: "Items",
  props: {
    title: String,
    price: Number,
    imgUrl: String

  }
};
</script>

<style>
    .centralizar{
        display: block;
    margin-left: auto;
    margin-right: auto
    }
</style>