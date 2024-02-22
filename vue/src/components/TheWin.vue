<template>
    <div class="grid grid-rows-3 h-72">
        <h1 v-if="winner==='player'" class="flex justify-center m-auto row-start-1 text-3xl font-bold underline">YOU WIN!!!!!</h1>
        <h2 v-if="winner==='player'" class="flex justify-center m-auto row-start-2 text-3xl font-bold underline">Score {{ p }} to {{ o }}</h2>
        <h1 v-if="winner==='computer'" class="flex justify-center m-auto row-start-1 text-3xl font-bold underline">YOU LOSE HAHA!!!!!</h1>
        <h2 v-if="winner==='computer'" class="flex justify-center m-auto row-start-2 text-3xl font-bold underline">Score {{ o }} to {{ p }}</h2>
        <button class="flex justify-center m-auto row-start-3 text-3xl font-bold" @click="$emit('return')">Go Back!</button>
    </div>
</template>

<script setup>
    const props= defineProps({
        winner:String,
        p:Number,
        o:Number
    })

</script>

<style  scoped>

</style>