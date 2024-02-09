<template>
    <div>
      <header class="grid grid-cols-4">
        <TheScoreboard class=" col-start-2 col-span-2 w-full"/>
        <h2 class="text-white h-12 shadow-2xl shadow-stone-400 rounded-lg hover:text-blue-400 flex w-32 underline m-auto items-center justify-center text-xl border-2 border-slate-700 bg-slate-600"><RouterLink to="/about">Moves List</RouterLink></h2>
  
      </header>
      <div class="flex items-center justify-center flex-col m-auto mt-36 h-72 w-2/3 bg-red-400 aspect-square border-8 border-black rounded-3xl"  v-if="gamestart">
      <WeaponChoose/>
      <button type="submit" value="PLAY GAME!" class="bg-white border-2 border-slate-300 w-52 hover:bg-slate-200 font-semibold" @click="toggle">Play Game!</button>
    </div>

     
    </div>
    <RouterView/>
  </template>

  <script setup>
  import TheScoreboard from '@/components/TheScoreboard.vue';
  import WeaponChoose from '@/components/WeaponChoose.vue';
  import { RouterView, RouterLink } from 'vue-router';
  import { ref } from 'vue';
  const gamestart = ref(true)
  function toggle(){
    gamestart.value= !gamestart.value
  }
  </script>

  <style scoped>
  
  </style>