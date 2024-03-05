<template>
  <div class="shopping-cart">
    <h1>Order Here</h1>
    <div v-if="store.length === 0">
      <h2>Your cart is empty</h2>
    </div>
    <div v-else>
      <div
        v-for="(Website, Price, netProfitPerMonth, Img) in store"
        class="website-item"
      >
        <h2 class="website-name">{{ Website }}</h2>
        <img :src="Img" :alt="'Picture of ' + Website" />
        <div class="net-profit-text">
          Net Profit Per Month: ${{ netProfitPerMonth }}
        </div>
        <div class="price-text">Price: ${{ Price }}</div>
        <button @click="removeFromCart(Website)">Remove From Cart</button>
      </div>
      <div class="total-prices-text">
        <h2>Total Net Profit Per Month:</h2>
        <h2>Total Price:</h2>
      </div>
    </div>
  </div>
</template>

<script setup>
import { store } from "@/stores/shoppingCart";

function removeFromCart(item) {}

function addNetProfit() {}

function addPrices() {}
</script>

<style lang="scss" scoped></style>
