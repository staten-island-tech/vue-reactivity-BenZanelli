<template>
    <div class= "scoreboard h-40 border-2 border-slate-700 bg-slate-600 m-auto text-center mt-3 rounded-3xl shadow-2xl shadow-stone-400 grid grid-rows-2 gap-y-3">
      <h1 class="text-pretty text-xl font-semibold text-white mt-3">Welcome to Fencing by Ben Zanelli ft Youwei Zhen</h1>
     <h1 class="scoretxt flex justify-center mt-6 text-white font-bold text-2xl underline w-full items-center">SCOREBOARD</h1>
     <div class="scores justify-center w-full h-12 grid grid-cols-3 mb-10">
        <div class="player flex justify-center flex-col"> 
            <h2 class="text-white text-xl underline">PLAYER</h2>
            <h3 @click="$emit('add1')" class="text-white aspect-square size-10 m-auto mt-1 text-xl under border-2 rounded-md border-red-500 bg-red-700">{{ pscore }}</h3>
        </div>
         <h3 class="mt-7 text-white">Selected Weapon: {{ wpn }}</h3>
        <div class="computer">
            <h2 class="text-white text-xl underline">OPPONENT</h2>
            <h3 @click="$emit('add2')" class="text-white aspect-square size-10 m-auto mt-1 text-xl border-2 rounded-md border-green-500 bg-green-700">{{ oscore }}</h3>
        </div>
       
    </div>
    
</div>
</template>

<script setup>
import { ref } from 'vue';

const props= defineProps({
  wpn:String,
  pscore:Number,
  oscore:Number
})

</script>

<style scoped>

</style>