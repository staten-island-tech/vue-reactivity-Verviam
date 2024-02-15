<template>
  <div>
    <WebsitesCard
      v-for="website in websites"
      :key="website.name"
      :Website="website"

      ></WebsitesCard>
  </div>
</template>

<!-- @click="addTocart(destination)" -->
<script setup>
import websites from '@/components/WebsitesCard.vue';
const websites = [
  {
    name: 
    price:
    img:
  }
]

</script>

<style lang="scss" scoped>

</style>