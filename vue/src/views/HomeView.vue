<script setup>
import TheScoreboard from '@/components/TheScoreboard.vue';
const test = [
  {name:"hi"}
]
</script>

<template>
  <main>
    <TheScoreboard
    v-for="thing in test"
    :key="thing.name"
    :tests="thing"
    ></TheScoreboard>
  </main>
</template>
