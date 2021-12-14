<template>
  <div class="buy">
    <button class="button button_plus" @click="plus">+</button>
    <span class="count">{{ count }}</span>
    <button class="button button_minus" @click="minus">-</button>
  </div>
</template>

<script>
export default {
  name: "Buy",
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
.buy {
  display: flex;
  flex-wrap: nowrap;
  justify-content: space-evenly;
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