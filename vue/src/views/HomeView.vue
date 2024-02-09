<template>
    <div>
      <header class="grid grid-cols-4">
        <TheScoreboard class=" col-start-2 col-span-2 w-full"/>
        <h2 class="text-white h-12 shadow-2xl shadow-stone-400 rounded-lg hover:text-blue-400 flex w-32 underline m-auto items-center justify-center text-xl border-2 border-slate-700 bg-slate-600"><RouterLink to="/about">Moves List</RouterLink></h2>
  
      </header>
     
  
     
    </div>
    <RouterView/>
  </template>
  
  <script setup>
  import TheScoreboard from '@/components/TheScoreboard.vue';
  import { RouterView, RouterLink } from 'vue-router';
  </script>
  
  <style scoped>
  
  </style>