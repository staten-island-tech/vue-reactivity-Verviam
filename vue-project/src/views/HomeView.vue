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
    url: "OfZenAndComputing.com",
    type:
    monetization:
    netProfit:
    price: "$4,823 /mo",
    description: "Passive & Growing 4yr old Tech & Gaming Blog with High DA & Extensive Opportunities for Growth, Generating $5,864/m in Net Profit w/ Diversified Income Streams",
    img: "https://d2jafhvbn4akdi.cloudfront.net/webp_c6f5edd0-5809-43bd-9ad6-807ad5c2f4ef.png",
    siteAge: 
  }
]

</script>

<style lang="scss" scoped>

</style>