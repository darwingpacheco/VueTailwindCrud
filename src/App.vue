<script setup>
import { ref } from 'vue';
import CardComponent from './components/CardComponent.vue';

const users = ref([
  {
    name: 'Darwin Gomez',
    mail: 'darwin@gmail.com'
  },
  {
    name: 'Andrey Pacheco',
    mail: 'pacheco@gmail.com'
  },

])
const borrarTarjeta = (index) => {
  alert('seguro de elimar',index)
  console.log('seguro de elimar', index)
  users.value.splice(index,1)
  console
}

let name, mail
const addUser = () => {
  const newUser = {
    name: name,
    mail: mail
  }
  users.value.unshift(newUser)
}
</script>

<template>
  <h1 class="text-2x1">
    HOLA MUNDO
  </h1>
  <input type="text" v-model="name"
  placeholder="Escriba su nombre" class="border rounded"><br><br>
  <input type="text" v-model="mail" placeholder="email" class="border rounded"><br>
  <button class="bg-green-600 px-2 py-1 rounded mt-2" @click="addUser">Añadir</button>
<div class="space-y-2">
  <CardComponent v-for="(user,index) in users" :key="index" 
  :name="user.name" :mail="user.mail" :index="index" @borrarTarjeta="borrarTarjeta"/>
</div>
</template>

<style scoped>

</style>
