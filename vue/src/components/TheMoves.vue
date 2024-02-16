<template>
    <div>
       <li>    
        {{ each.name }} moves:
        {{each.each}}
       </li>
    </div>
</template>

<script setup>
const props= defineProps({
    set:Object,
    each:Array
})

</script>

<style lang="scss" scoped>

</style>