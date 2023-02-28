<template>
  <h1 class="text-center text-5xl mb-10">codelzn's css playground</h1>
  <ul class="flex text-3xl justify-center items-center font-bold">
    <li
      v-for="sketch in sketchList"
      :key="sketch.path"
      class="hover:text-orange-300"
    >
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
<style lang="scss">
html,
body {
  width: 100%;
}
</style>
