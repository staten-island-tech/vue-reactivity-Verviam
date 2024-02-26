<template>
  <div class="card">
    <h1>Website Name: {{ Websites.name }}</h1>
    <img :src="Websites.img" alt="Picture of + {{ Websites.name }}" />
    <div class="type-text">Website Type: {{ Websites.type }}</div>
    <div class="moneitization-text">Moneitization: {{ Websites.monetization }}</div>
    <div class="net-profit-text">Net Profit Per Month: ${{ Websites.netProfitPerMonth }}</div>
    <div class="price-text">Price: ${{ Websites.price }}</div>
    <div class="description-text">{{ Websites.description }}</div>
    <button @click="addToCart" class="add-to-cart">Add to Cart</button>
  </div>
</template>

<script setup>
const props = defineProps({
  Websites: Object,
});
function addToCart() {
  
  //dom selector put into cart
}
</script>

<style lang="scss" scoped>
img {
  width: 250px;
  height: 250px;
}
.card {
  font-size: 3rem;
}

</style>
