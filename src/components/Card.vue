<template>
  <div class="card">
    <h4 class="title">{{ product.name }}</h4>
    <img class="img" v-bind:src="product.img" width="150" alt="">
    <p class="price">Цена: {{ product.price }}р</p>
    <buy/>
  </div>
</template>

<script>
import Buy from "@/components/Buy";

export default {
  name: "Card",
  components: {Buy},
  props: ['product'],
  comments: {
    Buy
  }
}
</script>

<style scoped>
  .card {
    margin: 5px;
    padding: 5px;

    border: black solid 1px;
    border-radius: 15px;
  }

  .title {
    color: red;
    text-align: right;
  }

  .img {
    display: block;
    text-align: center;
  }

  .price {
    text-align: left;
    color: darkblue;
  }
</style>