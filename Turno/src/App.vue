<script setup>

import MensajesDirectos from '@/components/MensajesDirectos.vue';
import { ref } from 'vue';


const mensajes = ref([{ id: 0, nombre:'hector', mensaje: 'hola como estas. Te amo'}, {id: 1, nombre:'diana', mensaje: 'hijo de puta'}, {id: 2, nombre:'juliana', mensaje: 'sapo hpta'}])

const mensajeSeleccionado = ref()
const nombreSeleccionado= ref()
function ShowMensaje(id){

  const mensaje = mensajes.value.find(m => m.id === id);

  const nombre = mensajes.value.find(m => m.id === id);

  nombreSeleccionado.value = nombre ? nombre.nombre : null;


  mensajeSeleccionado.value = mensaje ? mensaje.mensaje : null;
  


}

</script>

<template>
 
 
  <div class=" w-full bg-gray-800 h-screen flex">
    
      <div  class=" bg-gray-700 w-1/12">
        perfil
      </div>
      <div class=" text-center flex flex-col justify-evenly w-1/6 bg-gray-900">
          <div><h3 class=" text-white">Tendencias</h3></div>
          <div>
            
            <h3 class=" text-white">Mensajes directos</h3>
            
            <MensajesDirectos class="" v-for="(mensaje, index) in mensajes" :key="index" :id="mensaje.id"  :nombre="mensaje.nombre"  :mensaje="mensaje.mensaje" @ShowMensaje="ShowMensaje(mensaje.id)">

            </MensajesDirectos>
          
          </div>
      </div>

      <div class=" bg-gray-600 w-2/5">

        <div class=" w-4/5 my-0 mx-auto">
             <h1 class=" text-2xl font-semibold">{{ nombreSeleccionado }}</h1>

            <div class=" p-6 relative W-3/5 bg-gray-500 mt-6">
              <p >{{mensajeSeleccionado}}</p>

                
              <span class=" text-xs absolute bottom-0 right-0 p-2 mt-5 ">25/06/2023 10:55am </span>
                
            </div>

        </div>
       
      </div>

      <div class=" text-center  W-100%">

        <h2>PUBLICIDAD</h2>

      </div>

  </div>

</template>