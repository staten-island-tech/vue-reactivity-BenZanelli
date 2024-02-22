<template>
    <div>
        <h1>congrats!</h1>
        <h1 v-if="winner==='player'">YOU WIN!!!!!</h1>
        <h1 v-if="winner==='computer'">YOU LOSE HAHA!!!!!</h1>
    </div>
</template>

<script setup>
    const props= defineProps({
        winner:String
    })

</script>

<style  scoped>

</style>