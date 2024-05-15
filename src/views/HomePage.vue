<script setup>

import LayoutNavigation from "@/components/LayoutNavigation.vue";
import HomeBanner from "@/components/HomeBanner.vue";
import HomePart from "@/components/HomePart.vue";
</script>

<template>
<div class="home">
  <LayoutNavigation></LayoutNavigation>
  <HomeBanner></HomeBanner>
  <HomePart></HomePart>
</div>
</template>

<style scoped lang="scss">
.home {
  background-color: #ffffff;
}
</style>
