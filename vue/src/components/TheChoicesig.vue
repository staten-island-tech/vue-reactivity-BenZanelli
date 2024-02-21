<template>
    <div>
        <button @click="$emit('maybe')" v-for="move in display" class="flex px-5 border-2 border-black bg-slate-400 hover:bg-slate-500" :id="move" >{{ move }}</button>
    </div>
</template>

<script setup>
    const props = defineProps({
        wpn:String,
        moves:Object
    })
let display = []
if(props.wpn==="epee"){
    display = props.moves[0].each
}
else if(props.wpn==="foil"){
    display = props.moves[1].each
}
else{
    display = props.moves[2].each
}
function test(){
    console.log()
}

</script>

<style scoped>

</style>