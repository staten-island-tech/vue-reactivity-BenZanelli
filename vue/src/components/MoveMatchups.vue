<template>
  <div
    class="flex flex-col justify-center m-auto mt-6 bg-slate-500 rounded-full w-2/3 h-14 border-slate-600 border-4 text-white font-semibold underline hover:bg-slate-600 hover:border-slate-700"
  >
    <h1 v-if="result !== ''" class="flex justify-center">{{ result }}</h1>
    <div class="actions flex flex-row justify-center">
      <h2 v-if="result !== ''" class="mr-10">You're move: {{ move }}</h2>
      <h3 v-if="result !== ''">Computer move: {{ compmv }}</h3>
    </div>
    <button
      @click="
        test();
        $emit('blah', result);
        $emit('cdown', 5);
        $emit('combo', combo);
        $emit('img');
      "
      v-if="(move != '') & (result === '')"
    >
      <p>Confirm: {{ move }} and end turn?</p>
    </button>
  </div>
</template>

<script setup>
import { ref } from "vue";
const props = defineProps({
  move: String,
  weapon: String,
  compmv: String,
});
let result = ref("");
let combo = props.move.slice(0, 1) + props.compmv.slice(0, 1);
console.log(combo);

function test() {
  if (props.weapon === "epee") {
    if ((props.move === "Parry Arm") & (props.compmv === "Attack Chest")) {
      result.value = "They scored! :(";
    } else if ((props.move === "Parry Arm") & (props.compmv === "Attack Low")) {
      result.value = "They scored! :(";
    } else if ((props.move === "Parry Arm") & (props.compmv === "Fleche")) {
      result.value = "They scored! :(";
    } else if ((props.move === "Parry Arm") & (props.compmv === "Parry Low")) {
      result.value = "They scored! :(";
    } else if (
      (props.move === "Parry Chest") &
      (props.compmv === "Attack Arm")
    ) {
      result.value = "They scored! :(";
    } else if (
      (props.move === "Parry Chest") &
      (props.compmv === "Attack Low")
    ) {
      result.value = "They scored! :(";
    } else if (
      (props.move === "Parry Chest") &
      (props.compmv === "Parry Arm")
    ) {
      result.value = "They scored! :(";
    } else if (
      (props.move === "Parry Low") &
      (props.compmv === "Parry Chest")
    ) {
      result.value = "They scored! :(";
    } else if ((props.move === "Parry Low") & (props.compmv === "Attack Arm")) {
      result.value = "They scored! :(";
    } else if (
      (props.move === "Parry Low") &
      (props.compmv === "Attack Chest")
    ) {
      result.value = "They scored! :(";
    } else if ((props.move === "Parry Low") & (props.compmv === "Fleche")) {
      result.value = "They scored! :(";
    } else if ((props.move === "Fleche") & (props.compmv === "Parry Chest")) {
      result.value = "They scored! :(";
    } else if ((props.move === "Fleche") & (props.compmv === "Parry Arm")) {
      result.value = "They scored! :(";
    } else if (
      (props.move === "Fleche") &
      (props.compmv === "Counter Attack")
    ) {
      result.value = "They scored! :(";
    } else if (
      (props.move === "Counter Attack") &
      (props.compmv === "Parry Chest")
    ) {
      result.value = "They scored! :(";
    } else if (
      (props.move === "Counter Attack") &
      (props.compmv === "Parry Arm")
    ) {
      result.value = "They scored! :(";
    } else if (
      (props.move === "Counter Attack") &
      (props.compmv === "Parry Low")
    ) {
      result.value = "They scored! :(";
    } else if (
      (props.move === "Attack Chest") &
      (props.compmv === "Parry Chest")
    ) {
      result.value = "They scored! :(";
    } else if (
      (props.move === "Attack Chest") &
      (props.compmv === "Counter Attack")
    ) {
      result.value = "They scored! :(";
    } else if ((props.move === "Attack Chest") & (props.compmv === "Fleche")) {
      result.value = "They scored! :(";
    } else if (
      (props.move === "Attack Chest") &
      (props.compmv === "Attack Arm")
    ) {
      result.value = "They scored! :(";
    } else if ((props.move === "Attack Arm") & (props.compmv === "Parry Arm")) {
      result.value = "They scored! :(";
    } else if (
      (props.move === "Attack Arm") &
      (props.compmv === "Counter Attack")
    ) {
      result.value = "They scored! :(";
    } else if ((props.move === "Attack Arm") & (props.compmv === "Fleche")) {
      result.value = "They scored! :(";
    } else if (
      (props.move === "Attack Low") &
      (props.compmv === "Counter Attack")
    ) {
      result.value = "They scored! :(";
    } else if ((props.move === "Attack Low") & (props.compmv === "Parry Low")) {
      result.value = "They scored! :(";
    } else if (
      (props.move === "Attack Low") &
      (props.compmv === "Attack Chest")
    ) {
      result.value = "They scored! :(";
    } else if (
      (props.move === "Attack Low") &
      (props.compmv === "Attack Arm")
    ) {
      result.value = "They scored! :(";
    } else {
      result.value = "You scored! :)";
    }
    console.log(props.move, props.compmv, result.value);
  } else if (props.weapon === "foil") {
    if ((props.move === "Parry Shoulder") & (props.compmv === "Attack Chest")) {
      result.value = "They scored! :(";
    } else if (
      (props.move === "Parry Shoulder") &
      (props.compmv === "Counter Attack")
    ) {
      result.value = "They scored! :(";
    } else if (
      (props.move === "Parry Chest") &
      (props.compmv === "Attack Shoulder")
    ) {
      result.value = "They scored! :(";
    } else if (
      (props.move === "Parry Chest") &
      (props.compmv === "Parry Shoulder")
    ) {
      result.value = "They scored! :(";
    } else if (
      (props.move === "Counter Attack") &
      (props.compmv === "Parry Chest")
    ) {
      result.value = "They scored! :(";
    } else if (
      (props.move === "Counter Attack") &
      (props.compmv === "Parry Shoulder")
    ) {
      result.value = "They scored! :(";
    } else if (
      (props.move === "Attack Chest") &
      (props.compmv === "Parry Chest")
    ) {
      result.value = "They scored! :(";
    } else if (
      (props.move === "Attack Chest") &
      (props.compmv === "Attack Shoulder")
    ) {
      result.value = "They scored! :(";
    } else if (
      (props.move === "Attack Shoulder") &
      (props.compmv === "Parry Shoulder")
    ) {
      result.value = "They scored! :(";
    } else if (
      (props.move === "Attack Shoulder") &
      (props.compmv === "Counter Attack")
    ) {
      result.value = "They scored! :(";
    } else {
      result.value = "You scored! :)";
    }
  } else {
    if ((props.move === "Parry Mask") & (props.compmv === "Attack Arm")) {
      result.value = "They scored! :(";
    } else if (
      (props.move === "Parry Mask") &
      (props.compmv === "Attack Chest")
    ) {
      result.value = "They scored! :(";
    } else if ((props.move === "Parry Mask") & (props.compmv === "Flunge")) {
      result.value = "They scored! :(";
    } else if (
      (props.move === "Parry Mask") &
      (props.compmv === "Counter Attack")
    ) {
      result.value = "They scored! :(";
    } else if (
      (props.move === "Parry Chest") &
      (props.compmv === "Attack Arm")
    ) {
      result.value = "They scored! :(";
    } else if (
      (props.move === "Parry Chest") &
      (props.compmv === "Attack Mask")
    ) {
      result.value = "They scored! :(";
    } else if (
      (props.move === "Parry Chest") &
      (props.compmv === "Parry Arm")
    ) {
      result.value = "They scored! :(";
    } else if (
      (props.move === "Parry Chest") &
      (props.compmv === "Parry Mask")
    ) {
      result.value = "They scored! :(";
    } else if ((props.move === "Parry Arm") & (props.compmv === "Attack Mask")) {
        result.value = "They scored! :(";
    }else if ((props.move === "Parry Arm") & (props.compmv === "Attack Chest")) {
        result.value = "They scored! :(";
    }else if ((props.move === "Parry Arm") & (props.compmv === "Flunge")) {
        result.value = "They scored! :(";
    }else if ((props.move === "Parry Arm") & (props.compmv === "Attack Mask")) {
        result.value = "They scored! :(";
    } else if ((props.move === "Flunge") & (props.compmv === "Parry Chest")) {
        result.value = "They scored! :(";
    }else if ((props.move === "Flunge") & (props.compmv === "Counter Attack")) {
        result.value = "They scored! :(";
    }else if ((props.move === "Flunge") & (props.compmv === "Attack Mask")) {
        result.value = "They scored! :(";
    }else if ((props.move === "Flunge") & (props.compmv === "Attack Arm")) {
        result.value = "They scored! :(";
    }  else if ((props.move === "Counter Attack") &(props.compmv === "Parry Chest")) {
        result.value = "They scored! :(";
    } else if ((props.move === "Counter Attack") &(props.compmv === "Parry Arm")) {
        result.value = "They scored! :(";
    } else if ((props.move === "Counter Attack") &(props.compmv === "Attack Arm")) {
        result.value = "They scored! :(";
    } else if ((props.move === "Counter Attack") &(props.compmv === "Attack Mask")) {
        result.value = "They scored! :(";
    } else if ((props.move === "Attack Chest") &(props.compmv === "Parry Chest")) {
        result.value = "They scored! :(";
    }else if ((props.move === "Attack Chest") &(props.compmv === "Counter Attack")) {
        result.value = "They scored! :(";
    }else if ((props.move === "Attack Chest") &(props.compmv === "Flunge")) {
        result.value = "They scored! :(";
    }else if ((props.move === "Attack Chest") &(props.compmv === "Attack Arm")) {
        result.value = "They scored! :(";
    } else if ((props.move === "Attack Arm") & (props.compmv === "Parry Arm")) {
        result.value = "They scored! :(";
    }else if ((props.move === "Attack Arm") & (props.compmv === "Flunge")) {
        result.value = "They scored! :(";
    }else if ((props.move === "Attack Arm") & (props.compmv === "Attack Mask")) {
        result.value = "They scored! :(";
    } else if ((props.move === "Attack Mask") & (props.compmv === "Attack Chest")) {
      result.value = "They scored! :(";
    } else if ((props.move === "Attack Mask") & (props.compmv === "Parry Mask")) {
        result.value = "They scored! :(";
    } else {
      result.value = "You scored! :)";
    }
  }
}
</script>

<style scoped></style>
