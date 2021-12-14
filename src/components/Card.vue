<template>
  <div class="card">
    <h4 class="title">{{ product.name }}</h4>
    <img class="img" v-bind:src="product.img" width="150" alt="">
    <p class="price">Цена: {{ product.price }}р</p>
    <button class="button button_plus" @click="plus">+</button>
    <span class="count">{{ count }}</span>
    <button class="button button_minus" @click="minus">-</button>
  </div>
</template>

<script>
export default {
  name: "Card",
  props: ['product'],
  data() {
    return {
      count: 0
    }
  },
  methods: {
    plus: function() {
      this.count++;
    },
    minus: function() {
      if (this.count > 0) this.count--;
    }
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

  .count {
    text-align: center;
    color: black;
  }

  .button{
    width: 30px;

    border-radius: 10px;
    color: white;
  }
  .button_plus{
    background-color: green;
  }
  .button_minus{
    background-color: red;
  }
</style>