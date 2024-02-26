<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <header>
    <div class="wrapper">
      <h1>Websites For Sale</h1>
      <nav>
        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/shopping">Shopping Cart</RouterLink>
      </nav>
    </div>
  </header>

  <RouterView />
</template>

<style scoped>

.wrapper{
  font-size: 5rem;
}

</style>
