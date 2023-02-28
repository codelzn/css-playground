<template>
  <ul>
    <li v-for="sketch in sketchList" :key="sketch.path">
      <nuxt-link :to="sketch.path">{{ sketch.name }}</nuxt-link>
    </li>
  </ul>
</template>
<script setup lang="ts">
const sketchList = [
  {
    path: "/sketch01",
    name: "sketch01",
  },
];
</script>
<style scoped lang="scss"></style>
