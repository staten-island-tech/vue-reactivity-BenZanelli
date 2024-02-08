<template>
  <header>
    <div class= "scoreboard h-44 bg-slate-600 w-1/2 m-auto text-center mt-3 rounded-3xl shadow-2xl shadow-stone-400 grid grid-rows-2 gap-y-3">
     <h1 class="scoretxt flex justify-center mt-2.5 text-white font-bold text-3xl underline w-full items-center">SCOREBOARD</h1>
     <div class="scores justify-center w-full h-12 grid grid-cols-2">
        <div class="player flex justify-center flex-col">
            <h2 class="text-white text-xl underline">PLAYER</h2>
            <button @click="add1" class="text-white aspect-square size-10 m-auto mt-1 text-xl under border-2 rounded-md border-red-500 bg-red-700">{{ pscore }}</button>
        </div>
        <div class="computer">
            <h2 class="text-white text-xl underline">OPPONENT</h2>
            <button @click="add2" class="text-white aspect-square size-10 m-auto mt-1 text-xl border-2 rounded-md border-green-500 bg-green-700">{{ oscore }}</button>
        </div>
    </div>
</div>
  </header>
</template>

<script setup>
import { ref } from 'vue';
const pscore = ref(0);
function add1(){
  pscore.value++
}
const oscore = ref(0);
function add2(){
  oscore.value++
}


</script>

<style scoped>

</style>