<template>
  <div>
    <header class="grid grid-cols-4" v-if="!gamestart & !moveset">
      <TheScoreboard class="col-start-2 col-span-2 w-full" />
      <h2
        @click="moves"
        class="text-white h-12 shadow-2xl shadow-stone-400 rounded-lg hover:text-blue-400 flex w-32 underline m-auto items-center justify-center text-xl border-2 border-slate-700 bg-slate-600"
      >
        Move Sets
      </h2>
    </header>
    <div
      class="flex items-center justify-center flex-col m-auto mt-36 h-72 w-2/3 bg-red-400 aspect-square border-8 border-black rounded-3xl"
      v-if="gamestart"
    >
      <WeaponChoose @toggle="toggle" @getwpn="getWeapon" />
      
    </div>
    <button v-if="!gamestart & moveset" @click="moves">Go back</button>
  </div>
  <RouterView />
</template>

<script setup>
import TheScoreboard from "@/components/TheScoreboard.vue";
import WeaponChoose from "@/components/WeaponChoose.vue";
import { RouterView, RouterLink } from "vue-router";
import { ref } from "vue";
// import { chosen } from "../components/WeaponChoose.vue";
const gamestart = ref(true);
const moveset = ref(false);
const weapon = ref("")
function getWeapon(x) {
  console.log(x)
}
function toggle() {
  gamestart.value = !gamestart.value;
  getWeapon();
}
function moves() {
  moveset.value = !moveset.value;
}
const weapons = [
  {
    name: "epee",
  },
  {
    name: "foil",
  },
  {
    name: "sabre",
  },
];
</script>

<style scoped></style>
