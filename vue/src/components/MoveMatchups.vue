<template>
    <div>
        <h1 v-if="result!==''">{{ result }}</h1>
        <div class="actions">
            <h2 v-if="result!==''">{{ move }}</h2>
            <h3 v-if="result!==''">{{ compmv }}</h3>
        </div>
        <button @click="test" v-if="move!='' & result===''">Confirm: {{ move }}</button>
        <button @click="$emit('blah', result)" v-if="result!=''">End Turn?</button>
    </div>
</template>

<script setup>
import { ref } from 'vue';
const props = defineProps({
    move:String,
    weapon:String,
    compmv:String
})
let result = ref("")

function test(){
    if(props.weapon==="epee"){
    if(props.move==="Parry Arm" & props.compmv==="Attack Arm"){
        result.value="You scored!"
    }
    else if(props.move==="Parry Chest"&props.compmv==="Attack Chest"){
        result.value="You scored!"
    }
    else if(props.move==="Parry Low"&props.compmv==="Attack Low"){
        result.value="You scored!"
    }
    else if(props.move==="Fleche"&props.compmv!="Parry Chest"){
        result.value="You scored!"
    }
    else if(props.move==="Counter Attack"&props.compmv==="Attack Low"){
        result.value="You scored!"
    }
    else if(props.move==="Attack Chest" &props.compmv!="Parry Chest" ){
        result.value="You scored!"
    }
    else if(props.move==="Attack Arm"&props.compmv!="Parry Arm"){
        result.value="You scored!"
    }
    else if(props.move==="Attack Low"& props.compmv==="Counter Attack"){
        result.value="They scored!"
    }
    else if(props.move==="Attack Low"& props.compmv!="Parry Low"){
        result.value="You scored!"
    }
     else{
        result.value="They scored!"
    } 
    console.log(props.move, props.compmv, result.value)

}
}

</script>

<style  scoped>

</style>