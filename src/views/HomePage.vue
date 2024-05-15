<script setup>

import LayoutNavigation from "@/components/LayoutNavigation.vue";
import HomeBanner from "@/components/HomeBanner.vue";
import HomePart from "@/components/HomePart.vue";
import SideFloat from "@/components/SideFloat.vue";
</script>

<template>
<div class="home">
  <LayoutNavigation></LayoutNavigation>
  <HomeBanner></HomeBanner>
  <HomePart></HomePart>
  <SideFloat></SideFloat>
  <div class="patch" style="height: 150px"></div>
</div>
</template>

<style scoped lang="scss">
.home {
  background-color: #ffffff;
}
</style>
