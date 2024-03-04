<template>
  <div>
    <WebsitesCard
      v-for="website in websites"
      :key="website.name"
      :Websites="website"
      :Price="website.price"
      :netProfitPerMonth="website.netProfitPerMonth"
      @addToCart="addToCart(website)"

    ></WebsitesCard>
    <ShoppingCart
      v-for="(item, price, netProfitPerMonth) in shoppingCart"
      :key="item"
      :Website="item.website"
      :Price="price"
      :netProfitPerMonth="netProfitPerMonth"
      @removeFromCart="removeFromCart(item)"

    ></ShoppingCart>

  </div>
</template>


<script setup>
import WebsitesCard from '@/components/WebsitesCard.vue';
import ShoppingCart from '@/components/ShoppingCart.vue';
import { websites } from '@/stores/websiteArr';
import { store } from '@/stores/shoppingCart';


function addToCart(website) {
  store.shoppingCart.value.push({website, Price: website.price, netProfitPerMonth: website.netProfitPerMonth})
  console.log(store.shoppingCart)
}

function removeFromCart(item){

}

function addNetProfit(){

}

function addPrices(){
  
}


</script>

<style lang="scss" scoped></style>@/stores/shoppingCart