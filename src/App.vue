<template>
  <div id="app">
    <div>
      <p>Количество товара: {{ total_count }}</p>
      <p>Общая сумма: {{ total_price }}</p>
    </div>
    <div class="cards">
      <card v-for="product in products" :key="product.id" :product="product" @update-total="updateTotal"/>
    </div>
  </div>
</template>

<script>
import Card from './components/Card.vue'

export default {
  data() {
    return {
      products: [
        {
          id: 1,
          name: "Cat 1",
          price: 200,
          img: `https://ae01.alicdn.com/kf/H4921250a0de647c5a259c2de8558208b7/-.jpg_q50.jpg`
        },
        {
          id: 2,
          name: "Cat 2",
          price: 300,
          img: `https://ae01.alicdn.com/kf/H4921250a0de647c5a259c2de8558208b7/-.jpg_q50.jpg`
        },
        {
          id: 3,
          name: "Cat 3",
          price: 400,
          img: `https://ae01.alicdn.com/kf/H4921250a0de647c5a259c2de8558208b7/-.jpg_q50.jpg`
        },
      ],
      total_count: 0,
      total_price: 0
    }
  },
  name: 'App',
  components: {
    Card
  },
  methods: {
    updateTotal(dataCard) {
      this.total_count += dataCard.count; //BUG Исправить метод
    }
  }
}
</script>

<style>
.cards {
  display: flex;
  flex-wrap: wrap;
  flex-direction: row;
  justify-content: space-evenly;
}
</style>
