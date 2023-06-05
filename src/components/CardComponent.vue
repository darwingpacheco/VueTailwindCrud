<script setup>
const mensaje = () => {
   console.log('Diste click en la foto');
}
const props = defineProps(
    {
        name:{
            type: String,
            default: 'No name'
        },
        mail:{
            type: String,
            default: 'no email'
        }
    }
)
const borrarTarjeta = (index) => {
    console.log('borrar tarjeta', index)
    alert('borrar tarjeta', index)
    emit('borrarTarjeta', index)
}
const emit = defineEmits(['borrarTarjeta'])
</script>>

<template>
    <div class="w-48 rounded shadow overflow-hidden">
        <div class="inline-block">
            <img src="https://picsum.photos/40" alt="">
        </div>
        <div class="inline-block">
            <h2 class="text-sm font-semibold">{{props.name}}</h2>
            <p class="text-xs">{{props.mail}}</p>
        </div>

        <span class="inline-block ml-4 bg-red-600 text-white rounded leading-0 py-0 px-1 hover:cursor-pointer hover:bg-red-800" @click="borrarTarjeta(props.index)">
             X
         </span>
    </div>
   
</template>
