<script setup>
import { RouterLink, RouterView } from "vue-router";
import { ShoppingCartCount } from "./stores/shoppingCartCount";
</script>

<template>
  <header>
    <h1>Websites For Sale</h1>
    <nav class="wrapper">
      <RouterLink to="/">Home</RouterLink>
      <RouterLink to="/shopping">Shopping Cart</RouterLink>
      <h2>Items In Shopping Cart: {{ ShoppingCartCount.Count }}</h2>
    </nav>
  </header>

  <RouterView />
</template>

<style scoped>
.wrapper {
  justify-content: center;
}
</style>
