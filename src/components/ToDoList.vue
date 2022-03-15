<script setup>
import Chose from "../Chose";
import { reactive } from 'vue';
import ToDoListItem from './ToDoListItem.vue';
import ToDoForm from './ToDoForm.vue'; 
const listeC = reactive([new Chose("Ménage"), new Chose("Vaiselle")]);
function handlerFaire(index){
    listeC[index].faire();
}
function handlerDelete(index){
    listeC.splice(index,1);
}
function handlerAdd(l, q) {
    let p = new Chose(l, q);
    listeC.push(p);
}
</script>
<template>
 <h3>Liste des choses à faire</h3>
 <ToDoForm @addC="handlerAdd"></ToDoForm>
 <ul>
    <!-- <li v-for="(chose) in listeC" :key=[chose.id]>
        {{chose.pourAfficher()}}
        <div id="bouttons">
            <button v-on:click="handlerDelete(index)">Delete</button>
            <button v-on:click="handlerFaire(index)">Faire</button>
        </div>
     </li>-->
     <ToDoListItem
     v-for="(chose,index) of listeC"
     :key="chose.id"
     :chose="chose"
     :index="index"
     @deleteC="handlerDelete"
     @faireC="handlerFaire"
     />
 </ul>
</template>
<style scoped></style>