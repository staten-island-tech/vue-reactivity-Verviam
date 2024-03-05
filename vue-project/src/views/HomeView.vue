<template>
  <div class="everything">
    <WebsitesCard></WebsitesCard>
  </div>
</template>

<script setup>
import WebsitesCard from "@/components/WebsitesCard.vue";
</script>

<style lang="scss" scoped>
.everything {
  display: flex;
  flex-wrap: wrap;
}
</style>
