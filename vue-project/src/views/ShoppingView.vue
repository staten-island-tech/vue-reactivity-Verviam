<template>
  <div class="shopping-cart">
    <h1>Order Here</h1>
    <div v-if="store.length === 0">
      <h2>Your cart is empty</h2>
      <div class="total-prices-text"></div>
    </div>
    <div v-else>
      <div v-for="(Website, index) in store" :key="index" class="website-card">
        <h2 class="website-name">{{ Website.Website }}</h2>
        <img
          :src="Website.Img"
          :alt="'Pictuqre of ' + Website.Website"
          class="website-img"
        />
        <div class="net-profit-text">
          Net Profit Per Month: ${{ Website.netProfitPerMonth }}
        </div>
        <div class="price-text">Price: ${{ Website.Price }}</div>
        <button @click="removeFromCart(index)">Remove From Cart</button>
      </div>
    </div>
  </div>
</template>

<script setup>
import { store } from "@/stores/shoppingCartArr";
import { Price } from "@/stores/priceCounter";
import { netProfit } from "@/stores/netProfitCounter";
import { ShoppingCartCount } from "@/stores/shoppingCartCount";

function removeFromCart(index) {
  store.splice(index, 1);
  ShoppingCartCount.Count -= 1;
  Price.totalPrice -= store[index].Price;
  netProfit.netProfit -= store[index].netProfitPerMonth;
}
</script>

<style lang="scss" scoped>
.website-card {
  font-size: 3rem;
  padding: 2rem;
  margin: 2rem;
  display: flex;
  flex-wrap: wrap;
  width: 30%;
  outline: 0.2rem solid dimgray;
  justify-content: center;
}
.website-name {
  font-size: 2rem;
  display: flex;
  justify-content: center;
  margin: 2rem;
}
.website-img {
  height: 250px;
  width: 250px;
}
</style>
