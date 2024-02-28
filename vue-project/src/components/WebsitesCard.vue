<template>
  <div class="card">
    <h2 class="website-name">{{ Websites.name }}</h2>
    <img :src="Websites.img" alt="Picture of {{ Websites.name }}" />
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

const shoppingCart = []

function addToCart() {
  
  this.Websites.push(website)
  const addedWebsite = this.parentElemet;
  // key
  const websiteName = addedWebsite.querySelector(".website-name");
  shoppingCart.push(websiteName);
  console.log(shoppingCart)
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
  outline: 0.2rem solid #7FFF00;
  transition: all 0.2s ease-out;
}

.card:hover{
  transform: scale(1.03);
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
