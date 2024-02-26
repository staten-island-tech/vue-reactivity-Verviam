<template>
  <div class="card"><h1>{{ Websites.name }}</h1>
  <img :src="Websites.img" alt="Picture of + {{ Websites.name }}"/>
  <div class="type"> {{ Websites.type }}</div>
  <button @click="addToCart" class="add-to-cart">Add to Cart</button>
  </div>
</template>

<script setup>

const props = defineProps({
    Websites: Object,
})
function addToCart(){
  //dom selector put into cart
}
</script>

<style lang="scss" scoped>
img{
    width: 250px;
    height: 250px;

}
</style>