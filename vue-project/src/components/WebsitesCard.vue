<template>
  <div class="card" v-for="website in websites">
    <h2 class="website-name">{{ website.name }}</h2>
    <img :src="website.img" :alt="'Picture of ' + website.name" />
    <div class="websites-qualities-text">
      <div class="type-text">Website Type: {{ website.type }}</div>
      <div class="moneitization-text">Moneitization: {{ website.monetization }}</div>
      <div class="description-text">{{ website.description }}</div>
      <div class="net-profit-text">Net Profit Per Month: ${{ website.netProfitPerMonth }}</div>
      <div class="price-text">Price: ${{ website.price }}</div>
    </div>
      <button @click="addToCart(website)">Add To Cart</button> 
    </div>
  
</template>

<script setup>
import { websites } from '@/stores/websiteArr';
import { store } from '@/stores/shoppingCart';

function addToCart(website) {
  store.shoppingCart.push({
    website, 
    Price: website.price, 
    netProfitPerMonth: website.netProfitPerMonth
  })
  console.log(store.shoppingCart)
}
</script> 

<style lang="scss" scoped>
img {
  width: 250px;
  height: 250px;
}

.card {
  font-size: 3rem;
  padding: 2rem;
  margin: 2rem;
  display: flex;
  flex-wrap: wrap;
  width: 25%;
  outline: 0.2rem solid #7FFF00
}

.websites-qualities-text{
  font-size: 1em;
  padding: 1em;
  text-align: center;
}
.description-text{
  padding: 2em;
}

@media screen and (max-width: 1080px) {
  .card {
    width: 25%;
  }
}

@media screen and (max-width: 800px) {
  .card {
    width: 40%;
  }
}

@media screen and (max-width: 600px) {
  .card {
    width: 60%;
  }
}

@media screen and (max-width: 400px) {
  .card {
    width: 100%;
  }
}
</style>
