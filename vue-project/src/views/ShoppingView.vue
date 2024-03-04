<template>
  <div>
    <ShoppingCart
      v-if="shoppingCart.length > 0" 
      v-for="websiteObj in shoppingCart"
      :key="websiteObj.name"
      :Website="websiteObj"
      :Price="websiteObj.price"
      :netProfitPerMonth="websiteObj.netProfitPerMonth"
      @removeFromCart="removeFromCart(position)"

    ></ShoppingCart>
    
  </div>
</template>

<script setup>
import ShoppingCart from '@/components/ShoppingCart.vue';
</script>

<style lang="scss" scoped>

</style>