<template>
  <div class="grid grid-rows-4">
    <header class="grid grid-cols-4 row-start-1" v-if="!gamestart & !moveset">
      <TheScoreboard class="col-start-2 col-span-2 w-full" />
      <h2
        @click="movie"
        class="text-white h-12 shadow-2xl shadow-stone-400 rounded-lg hover:text-blue-400 flex w-32 underline m-auto items-center justify-center text-xl border-2 border-slate-700 bg-slate-600"
      >
        Move Sets
      </h2>
    </header>
    <div class="moves" v-if="!gamestart & moveset">
    <TheMoves
    v-for="thing in moves" :key="thing.name" :each="thing" :moves="thing.each" :boom="thing.name" />
    </div>
    <div
      class="flex items-center justify-center flex-col m-auto mt-36 h-72 w-2/3 bg-red-400 aspect-square border-8 border-black rounded-3xl"
      v-if="gamestart"
    >
      <WeaponChoose @toggle="toggle" @getwpn="getWeapon"/>
      
    </div>
    <button v-if="!gamestart & moveset" @click="movie" class="bg-slate-500 text-white w-1/3 m-auto h-1/2 hover:bg-slate-700 duration-300 rounded-full">Go back</button>
    <div class="strip flex flex-col row-start-2 row-span-2" v-if="!gamestart & !moveset">
      <div class="icons flex flex-row justify-around">
      </div>
    </div>
   

    
  </div>
  <RouterView />
</template>

<script setup>
import TheScoreboard from "@/components/TheScoreboard.vue";
import WeaponChoose from "@/components/WeaponChoose.vue";
import { RouterView, RouterLink } from "vue-router";
import { ref } from "vue";
import ThePlayer from "@/components/ThePlayer.vue";
import TheComputer from "@/components/TheComputer.vue";
import TheMoves from "@/components/TheMoves.vue";
// import { chosen } from "../components/WeaponChoose.vue";
const gamestart = ref(true);
const moveset = ref(false);
let weapon = ""
function getWeapon(x) {
  weapon = x
  console.log(weapon)
}
function toggle() {
  gamestart.value = !gamestart.value;
  getWeapon();
}
function movie() {
  moveset.value = !moveset.value;
}
const moves = [
   {
    name:"Epee",
    each:["Lunge", "Parry 6","Parry 4","Parry 2","Parry 8","Fleche","Counter attack","Attack chest","Attack arm","Attack low","Beat 6","Beat 4","Beat 5"]
  },
  {
    name: "Foil",
    each:["Lunge","Parry 6","Parry 4","fleche","Counter attack","Attack shoulder","Attack chest","Beat 4","Beat 5"]
},
{  name:"Sabre",
    each:["Lunge","Flunge","Counter attack","Parries 1-8"]
}
]
 
  
</script>

<style scoped></style>
