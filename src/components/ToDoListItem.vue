<script setup>
defineProps(["chose","index"]);
</script>
<template>
 <li>{{ chose.pourAfficher() }}
        <button @click="$emit('deleteC',index)">Delete</button>
        <button @click="$emit('faireC',index)">Faire</button>
 </li>
</template>
<style>
</style>