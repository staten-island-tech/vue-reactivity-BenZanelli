<template>
  <div class="grid grid-rows-4">
    <header class="grid grid-cols-4 row-start-1" v-if="!gamestart & !moveset">
      <TheScoreboard class="col-start-2 col-span-2 w-full" :wpn="weapon" :pscore="pscore" :oscore="oscore" @add1="add1" @add2="add2" />
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
    <button v-if="!gamestart & moveset" @click="movie" class="bg-slate-500  border-4 border-slate-600 text-white w-1/4 m-auto h-1/3 hover:bg-slate-700 hover:border-slate-800 duration-300 rounded-full">Go back</button>
    <div class="strip flex flex-col row-start-2 row-span-2" v-if="!gamestart & !moveset">
      <div class="icons flex flex-row justify-around">
      </div>
    <MoveMatchups :compmv="compmv" :move="playermv" :weapon="weapon" />
    <div class="game grid grid-cols-5 grid-rows-6 h-full mt-6">
      <TheChoicesig @maybe="test"  :wpn="weapon" :moves="moves" class=" col-start-1 col-span-5 row-start-6 flex justify-center  border-4 border-slate-600 rounded-xl w-fit m-auto h-full"/>
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
import TheChoicesig from "@/components/TheChoicesig.vue";
import MoveMatchups from "@/components/MoveMatchups.vue";
// import { chosen } from "../components/WeaponChoose.vue";
const gamestart = ref(true);
const moveset = ref(false);
let weapon = ""
const pscore = ref(0)
const oscore = ref(0)
function add1(){
  pscore.value++
}
function add2(){
  oscore.value++
}
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
    each:["Parry Arm","Parry Chest","Parry Low","Fleche","Counter Attack","Attack Chest","Attack Arm","Attack Low",]
  },
  {
    name: "Foil",
    each:["Parry Shoulder","Parry Chest","Fleche","Counter Attack","Attack Shoulder","Attack Chest"]
},
{  name:"Sabre",
    each:["Flunge","Counter Attack","Attack Chest","Attack Arm","Attack Mask","Parry Mask", "Parry Chest", "Parry Arm"]
}
]
let display =[]
let compmv = ref("")
let playermv= ref("")
function test(n){
  playermv.value = n
  console.log(playermv.value)
  if(weapon==="epee"){
    display = moves[0].each
  }
  else if(weapon==="foil"){
    display = moves[1].each
  }
  else{
    display = moves[2].each
  }
  console.log(display)
  compmv.value = display[(Math.floor(Math.random()*display.length))]
  console.log(compmv.value);
}
let result=""
function thing(x){
  result=x
  console.log(result)
}
/* let count = 60;
const timer = setInterval(function() {
  count--;
  console.log(count);
  if (count === 0) {
    clearInterval(timer);
    console.log("Time's up!");
  }
}, 1000); */

</script>

<style scoped></style>
