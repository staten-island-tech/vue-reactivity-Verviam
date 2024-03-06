<script setup>
import { RouterLink, RouterView } from "vue-router";
import { ShoppingCartCount } from "./stores/shoppingCartCount";
import { netProfit } from "./stores/netProfitCounter";
import { Price } from "./stores/priceCounter";
</script>

<template>
  <header>
    <h1>Websites For Sale</h1>
    <nav class="wrapper">
      <RouterLink to="/">Home</RouterLink>
      <RouterLink to="/shopping">Shopping Cart</RouterLink>
      <h2>Items In Shopping Cart: {{ ShoppingCartCount.Count }}</h2>
      <h2>Total Net Profit Per Month: ${{ netProfit.netProfit }}</h2>
      <h2>Total Price: ${{ Price.totalPrice }}</h2>
    </nav>
  </header>

  <RouterView />
</template>

<style scoped>
.wrapper {
  justify-content: center;
}
</style>
