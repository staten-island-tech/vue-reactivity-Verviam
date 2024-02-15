<template>
  <div>
    <WebsitesCard
      v-for="website in websites"
      :key="website.url"
      :Website="website"

      ></WebsitesCard>
  </div>
</template>

<!-- @click="addTocart(destination)" -->
<script setup>
import WebsitesCard from '@/components/WebsitesCard.vue';
const websites = [
  {
    url: "OfZenAndComputing.com",
    type: "Content", 
    monetization: "Affiliate Sales",
    netProfitPerMonth: 4823, 
    price: 153000,
    description: "Passive & Growing 4yr old Tech & Gaming Blog with High DA & Extensive Opportunities for Growth, Generating $5,864/m in Net Profit w/ Diversified Income Streams",
    img: "https://d2jafhvbn4akdi.cloudfront.net/webp_c6f5edd0-5809-43bd-9ad6-807ad5c2f4ef.png",
    siteAge: "3 years"
  }
]

</script>

<style lang="scss" scoped>

</style>