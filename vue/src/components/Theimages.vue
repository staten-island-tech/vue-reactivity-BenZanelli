<template>
    <div>
       <img :src="img" alt="">
    </div>
</template>

<script setup>
const props = defineProps({
    weapon: String,
    mvcmbo: String,
    move: String,
    commv: String,
    img: String
})

</script>

<style scoped>

</style>