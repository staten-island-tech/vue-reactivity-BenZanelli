<template>
    <div>
        <h1 v-if="result!==''">{{ result }}</h1>
        <div class="actions">
            <h2 v-if="result!==''">{{ move }}</h2>
            <h3 v-if="result!==''">{{ compmv }}</h3>
        </div>
        <button @click="test();$emit('blah', result);$emit('cdown',5) " v-if="move!='' & result===''">Confirm: {{ move }} and end turn?</button>
       
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
    else if(props.weapon==="foil"){
        if(props.move==="Parry Shoulder" & props.compmv==="Attack Shoulder"){
        result.value="You scored!"
    }
    else if(props.move==="Parry Chest"&props.compmv==="Attack Chest"){
        result.value="You scored!"
    }
    else if(props.move==="Fleche"&props.compmv!="Parry Chest"){
        result.value="You scored!"
    }
    else if(props.move==="Counter Attack"&props.compmv==="Parry Shoulder"){
        result.value="You scored!"
    }
    else if(props.move==="Attack Chest" &props.compmv!="Parry Chest" ){
        result.value="You scored!"
    }
    else if(props.move==="Attack Shoulder"&props.compmv!="Parry Shoulder"){
        result.value="You scored!"
    }
     else{
        result.value="They scored!"
    } 
    }
    else{
        if(props.move==="Parry Mask" & props.compmv==="Attack Mask"){
        result.value="You scored!"
    }
    else if(props.move==="Parry Chest"&props.compmv==="Attack Chest"){
        result.value="You scored!"
    }
    else if(props.move==="Parry Arm"&props.compmv==="Attack Arm"){
        result.value="You scored!"
    }
    else if(props.move==="Flunge"&props.compmv!="Parry Chest"){
        result.value="You scored!"
    }
    else if(props.move==="Counter Attack"&props.compmv==="Attack Mask"){
        result.value="You scored!"
    }
    else if(props.move==="Attack Chest" &props.compmv!="Parry Chest" ){
        result.value="You scored!"
    }
    else if(props.move==="Attack Arm"&props.compmv!="Parry Arm"){
        result.value="You scored!"
    }
    else if(props.move==="Attack Mask"& props.compmv==="Counter Attack"){
        result.value="They scored!"
    }
    else if(props.move==="Attack Mask"& props.compmv!="Parry Mask"){
        result.value="You scored!"
    }
     else{
        result.value="They scored!"
    } 
    }
}

</script>

<style  scoped>

</style>