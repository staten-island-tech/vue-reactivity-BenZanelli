<template>
  <div
    class="grid grid-rows-3 h-72 bg-slate-500 w-1/3 justify-center m-auto rounded-2xl border-2 border-slate-700 shadow-2xl shadow-black text-slate-900"
  >
    <h1
      v-if="winner === 'player'"
      class="flex justify-center m-auto row-start-1 text-3xl font-bold bg-slate-400 border-2 border-slate-700"
    >
      YOU WIN!!!!!
    </h1>
    <h2
      v-if="winner === 'player'"
      class="flex justify-center m-auto row-start-2 text-3xl font-bold bg-slate-400 border-2 border-slate-700"
    >
      Score {{ p }} to {{ o }}
    </h2>
    <h1
      v-if="winner === 'computer'"
      class="flex justify-center m-auto row-start-1 text-3xl font-bold bg-slate-400 border-2 border-slate-700"
    >
      YOU LOSE HAHA!!!!!
    </h1>
    <h2
      v-if="winner === 'computer'"
      class="flex justify-center m-auto row-start-2 text-3xl font-bold bg-slate-400 border-2 border-slate-700"
    >
      Score {{ o }} to {{ p }}
    </h2>
    <button
      class="inline-block justify-center m-auto row-start-3 text-3xl font-bold border-2 bg-slate-600 text-white rounded-md border-slate-50 w-full h-12 align-middle"
      @click="$emit('return')"
    >
      Go Back!
    </button>
  </div>
</template>

<script setup>
const props = defineProps({
  winner: String,
  p: Number,
  o: Number,
});
</script>

<style scoped></style>
