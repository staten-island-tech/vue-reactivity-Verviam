<template>
  <div class="shopping-cart">
      <h1>Shopping Cart</h1>
      <div class="websites-qualities-text">
      <h2 class="website-name">{{ Website.name }}</h2>
      <img :src="Website.img" :alt="'Image of ' + Website.name">
      <p class="net-profit-text">Net Profit Per Month: ${{ netProfitPerMonth }}</p>
      <p class="price-text">Price: ${{ Price }}</p>
      </div>
      <button @click="$emit('removeFromCart')">Remove From Cart</button>

  </div>
</template>

<script setup>
import { defineProps } from 'vue';

const props = defineProps({
  Website: Object,
  Price: Number,
  netProfitPerMonth: Number
})
</script>

<style lang="scss" scoped>
@media (min-width: 1024px) { 
  .shopping-cart {
    font-size: 5rem;
    display: flex;
    align-items: center;
  }
}


</style>