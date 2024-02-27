<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <header>
    <h1>Websites For Sale</h1>
    <nav class="wrapper">
      <RouterLink to="/">Home</RouterLink>
      <RouterLink to="/shopping">Shopping Cart</RouterLink>
    </nav>
  </header>

  <RouterView />
</template>

<style scoped>
.wrapper{
  justify-content: center;
}
</style>
