<template>
  <h1 class="text-pretty text-4xl underline font-semibold">
    Choose Your Weapon
  </h1>
  <div class="choices">
    <form
      action=""
      class="flex items-center justify-center flex-col"
      id="form"
      @submit.prevent
    >
      <div class="ep flex flex-row mb-2 mt-2">
        <input type="radio" id="epee" name="weapon" value="epee" />
        <label for="epee">EPEE</label><br />
      </div>
      <div class="fl flex flex-row mb-2">
        <input type="radio" id="foil" name="weapon" value="foil" />
        <label for="foil">FOIL</label><br />
      </div>
      <div class="sbr flex flex-row mb-2">
        <input type="radio" id="sabre" name="weapon" value="sabre" />
        <label for="sabre">SABRE</label><br />
      </div>
    </form>
  </div>
</template>

<script setup>
import { ref } from "vue";
import { RouterLink, RouterView } from "vue-router";
const form = document.querySelector("#form");
const props = defineProps({
  gamestart: Boolean,
  chosen: String,
});
const chosen = ref("");
</script>
<style scoped></style>
