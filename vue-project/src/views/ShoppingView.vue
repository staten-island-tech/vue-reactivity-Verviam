<template>
  <div>
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
import ShoppingCart from '@/components/ShoppingCart.vue';

</script>

<style lang="scss" scoped>

</style>