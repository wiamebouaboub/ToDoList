<script setup>
import { ref } from "vue";
const libelle =ref("")
</script>
<template>
 <form @submit.prevent="$emit('addC', libelle)">
     <form @submit.prevent="handlderAdd(libelle, qte)"></form>
     <input type="text" v-model="libelle" placeholder="Chose"/>
     <input type="submit" value="Valider"/>
 </form>
</template>
<style scoped>
</style>