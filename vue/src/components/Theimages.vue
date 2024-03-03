<template>
  <div>
    <img
      class="aspect-[17/9] duration-300 border-2 border-black rounded-sm shadow-lg shadow-black w-full"
      :src="img"
      alt=""
    />
  </div>
</template>

<script setup>
import { watch } from 'vue';

const props = defineProps({
  weapon: String,
  mvcmbo: String,
  move: String,
  commv: String,
  img: String,
});
watch()
</script>

<style scoped></style>
