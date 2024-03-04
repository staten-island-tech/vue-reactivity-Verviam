<template>
  <div class="card">
    <h2 class="website-name">{{ Websites.name }}</h2>
    <img :src="Websites.img" :alt="'Picture of ' + Websites.name" />
    <div class="websites-qualities-text">
      <div class="type-text">Website Type: {{ Websites.type }}</div>
      <div class="moneitization-text">Moneitization: {{ Websites.monetization }}</div>
      <div class="description-text">{{ Websites.description }}</div>
      <div class="net-profit-text">Net Profit Per Month: ${{ netProfitPerMonth }}</div>
      <div class="price-text">Price: ${{ Price }}</div>
    </div>
      <button @click="$emit('addToCart', props.Websites)">Add To Cart</button> 
    </div>
  
</template>

<script setup>
import { defineProps } from 'vue';

const props = defineProps({
  Websites: Object,
  netProfitPerMonth: Number,
  Price: Number
});

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
