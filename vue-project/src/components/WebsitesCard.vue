<template>
  <div class="card" v-for="website in websites">
    <h2 class="website-name">{{ website.name }}</h2>
    <img :src="website.img" :alt="'Picture of ' + website.name" />
    <div class="websites-qualities-text">
      <div class="type-text">Website Type: {{ website.type }}</div>
      <div class="moneitization-text">
        Moneitization: {{ website.monetization }}
      </div>
      <div class="description-text">{{ website.description }}</div>
      <div class="net-profit-text">
        Net Profit Per Month: ${{ website.netProfitPerMonth }}
      </div>
      <div class="price-text">Price: ${{ website.price }}</div>
    </div>
    <button
      @click="
        addToCart(
          website.name,
          website.price,
          website.netProfitPerMonth,
          website.img
        )
      "
    >
      Add To Cart
    </button>
  </div>
</template>

<script setup>
import { websites } from "@/stores/websiteArr";
import { store } from "@/stores/shoppingCartArr";
import { ShoppingCartCount } from "@/stores/shoppingCartCount";
import { Price } from "@/stores/priceCounter";
import { netProfit } from "@/stores/netProfitCounter";

function addToCart(name, price, netProfitPerMonth, img) {
  addNetProfit(netProfitPerMonth);
  addPrices(price);
  store.push({
    Website: name,
    Price: price,
    netProfitPerMonth: netProfitPerMonth,
    Img: img,
  });
  ShoppingCartCount.Count += 1;
  console.log(store);
}

function addNetProfit(netProfitPerMonth) {
  netProfit.netProfit += netProfitPerMonth;
}
function addPrices(price) {
  Price.totalPrice += price;
}
</script>

<style lang="scss" scoped>
img {
  width: 300px;
  height: auto;
  margin: 2rem;
}

.card {
  font-size: 3rem;
  padding: 2rem;
  margin: 2rem;
  display: flex;
  flex-wrap: wrap;
  width: 30%;
  outline: 0.2rem solid dimgray;
  justify-content: center;
}

.websites-qualities-text {
  font-size: 1em;
  padding: 0.5rem;
  text-align: center;
  color: dimgray;
}
.description-text {
  padding: 2em;
}
.website-name {
  display: flex;
  justify-content: center;
  margin: 2rem;
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
