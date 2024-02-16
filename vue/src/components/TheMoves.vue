<template>
    <div>
        <ol>
       <div class="flex flex-row bg-slate-500 mb-10 text-white justify-center w-2/3 m-auto rounded-full mt-10">    
        <p >{{ boom }} moves are:</p>
        <p v-for="move in moves" class="underline px-3">
            {{ move }}
        </p>
    </div>
    </ol>
    </div>
</template>

<script setup>
const props= defineProps({
    set:Object,
    boom: String,
    moves: Array,
})

console.log(props.moves[0].each)
</script>

<style lang="scss" scoped>

</style>