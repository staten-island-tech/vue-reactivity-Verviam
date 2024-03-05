<template>
  <div class="shopping-cart">
    <h1>Order Here</h1>
    <div v-if="store.length === 0">
      <h2>Your cart is empty</h2>
    </div>
    <div v-else>
      <div v-for="Website in store" class="website-item">
        <h2 class="website-name">{{ Website.Website }}</h2>
        <img :src="Website.Img" :alt="'Picture of ' + Website.Website" />
        <div class="net-profit-text">
          Net Profit Per Month: ${{ Website.netProfitPerMonth }}
        </div>
        <div class="price-text">Price: ${{ Website.Price }}</div>
        <button @click="removeFromCart(Website)">Remove From Cart</button>
      </div>
      <div class="total-prices-text">
        <h2>Total Net Profit Per Month: ${{ addedNetProfit }}</h2>
        <h2>Total Price: ${{ addedPrices }}</h2>
      </div>
    </div>
  </div>
</template>

<script setup>
import { store } from "@/stores/shoppingCartArr";
import { Price } from "@/stores/priceCounter";
import { netProfit } from "@/stores/netProfitCounter";

function removeFromCart(website) {}

function addedNetProfit() {
  netProfit;
}

function addedPrices() {
  Price;
}
</script>

<style lang="scss" scoped>
.website-item {
  font-size: 3rem;
}
.website-name {
  font-size: 2rem;
}
</style>
@/stores/shoppingCartArr
