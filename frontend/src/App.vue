<script setup lang="ts">
import { ref,reactive } from 'vue';
const todos : any= reactive([
  {description: 'Estudar Typescript', done: true},
  {description: 'Fazer a prova Online', done: false},
  {description: 'Cortar a grama', done: false},
])
const description = ref('');

function addItem (){
   todos.push({description: description.value,done:false})
   description.value='';
}
</script>

<template>
  <div v-for="item in todos">
    <p><span :style="{'text-decoration':(item.done)?'line-through':''}">{{item.description}}</span> {{ item.done }}</p>
  </div>
  {{ description }}
  <input type="text" v-model="description"/>
  <button v-on:click="addItem()">Add</button>
</template>

<style scoped>

</style>
