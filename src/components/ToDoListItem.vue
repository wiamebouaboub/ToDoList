<script setup>
defineProps(["chose","index"]);
</script>
<template>
 <li>{{ chose.pourAfficher() }}
        <button @click="$emit('deleteC',index)">Supprimer</button>
        <button @click="$emit('faireC',index)">Fait</button>
 </li>
</template>
<style>
</style>