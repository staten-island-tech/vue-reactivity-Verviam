<template>
  <div class="shopping-cart">
    <h1>Order Here</h1>
    <div v-if="store.length === 0">
      <h2>Your cart is empty</h2>
    </div>
    <div v-else>
      <div v-for="website in websites" class ="website-item">
        <h2 class="website-name">{{ website.name }}</h2>
        <img :src="website.img" :alt="'Picture of ' + website.name" />
        <div class="net-profit-text">Net Profit Per Month: ${{ website.netProfitPerMonth }}</div>
        <div class="price-text">Price: ${{ website.price }}</div>
        <button @click="removeFromCart(website)">Remove From Cart</button> 
      </div>
      <div class="total-prices-text">
        <h2>Total Net Profit Per Month: </h2>
        <h2>Total Price: </h2>
      </div>
    </div>
  </div>
</template>

<script setup>
import { store } from '@/stores/shoppingCart';
import { websites } from '@/stores/websiteArr';

function removeFromCart(item){

}

function addNetProfit(){

}

function addPrices(){
  
}

</script>

<style lang="scss" scoped>

</style>