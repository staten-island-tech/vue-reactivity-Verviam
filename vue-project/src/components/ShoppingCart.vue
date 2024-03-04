<template>
  <div class="shopping-cart">
      <h1>Shopping Cart</h1>
      <h2 class="website-name">{{ Website.name }}</h2>
      <img :src="Website.img" :alt="'Image of ' + Website.name">
      <button @click="$emit('removeFromCart')">Remove From Cart</button>
  </div>
</template>

<script setup>
import { defineProps } from 'vue';

const props = defineProps({
  Website: Object,
  price: Number,
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