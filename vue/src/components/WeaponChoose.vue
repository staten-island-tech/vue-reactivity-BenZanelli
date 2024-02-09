<template>
<div class="flex items-center justify-center flex-col m-auto mt-40 h-60 w-2/3 bg-red-400 aspect-square border-8 border-black rounded-3xl">
    <h1 class=" text-pretty text-4xl underline font-semibold">Choose Your Weapon</h1>
    <div class="choices">
        <form action="" class="flex items-center justify-center flex-col" id="form">
            <div class="ep flex flex-row mb-2 mt-2">
            <input type="radio" id="epee" name="weapon" value="epee">
            <label for="epee">EPEE</label><br>
            </div>
            <div class="fl flex flex-row mb-2">
            <input type="radio" id="foil" name="weapon" value="foil">
            <label for="foil">FOIL</label><br>
            </div>
            <div class="sbr flex flex-row mb-2">
                 <input type="radio" id="sabre" name="weapon" value="sabre">
                <label for="sabre">SABRE</label><br>
        </div>
            <button @click="test" type="submit" value="PLAY GAME!" class="bg-white border-2 border-slate-300 w-52 hover:bg-slate-200 font-semibold">PLAY GAME!</button>
        </form> 
    </div>
</div>
</template>

<script setup>
import {ref} from  'vue'
const form= document.querySelector("#form")

function test(){
    console.log(form.value)
}
</script>

<style scoped>

</style>