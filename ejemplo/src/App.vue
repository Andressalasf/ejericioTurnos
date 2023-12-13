<script setup>
import { ref } from 'vue';


let notifiLike = ref(0)
let notifiDislike = ref(0)

function ValueLike(){

  if (notifiLike.value == 0 ){
    notifiLike.value++;
  }
  minutosValueDislike()
 
}

function minutosValueLike(){
  if(notifiLike.value >=1){
      notifiLike.value--
  }
}

function ValueDislike(){
  if (notifiDislike.value == 0 ){
    notifiDislike.value++;
  }
  minutosValueLike()

  
}

function minutosValueDislike(){
  if(notifiDislike.value >=1){
      notifiDislike.value--
  }
}

</script>

<template>
 
    <div class=" w-screen h-[100%] bg-slate-200 ">
      <div class=" w-4/5 my-0 mx-auto h-full ">

        <div class="">

            <div class="flex justify-between  w-4/5 mb-6 py-4 ">
              <p>Historias</p>
              <p>Todas</p>
            </div>          
            <div class=" flex justify-between  w-4/5 items-center ">
              <div class=" bg-blue-500 mx-4 rounded-sm"  ><img class= " my-0 mx-auto w-4/5 h-4/5 rounded-sm  py-2  " src="https://apicongresovisible.uniandes.edu.co/uploads/persona/811/figura-Gustavo%20Petro-510px.jpg" alt=""> </div>
              <div class=" bg-blue-500 mx-4  rounded-sm"><img class= "my-0 mx-auto w-4/5 h-4/5  rounded-sm py-2 " src="https://apicongresovisible.uniandes.edu.co/uploads/persona/811/figura-Gustavo%20Petro-510px.jpg" alt=""></div>
              <div class=" bg-slate-500 mx-4 rounded-sm"><img class= "my-0 mx-auto w-4/5 h-4/5  rounded-sm py-2  " src="https://apicongresovisible.uniandes.edu.co/uploads/persona/811/figura-Gustavo%20Petro-510px.jpg" alt=""></div>
              <div class=" bg-slate-500 mx-4 rounded-sm"><img class= "my-0 mx-auto w-4/5 h-4/5  rounded-sm py-2 " src="https://apicongresovisible.uniandes.edu.co/uploads/persona/811/figura-Gustavo%20Petro-510px.jpg" alt=""></div>
            </div>
        </div>
        <div class=" w-4/5 flex justify-between h-30 mt-8 mb-4 items-center ">
            <div class="flex w-2/5 ">
                <div class="w-2/4"><img class= " my-0 mx-auto w-14 h-14 rounded-full  py-2  " src="https://apicongresovisible.uniandes.edu.co/uploads/persona/811/figura-Gustavo%20Petro-510px.jpg" alt=""></div>
                <div class="w-4/5"><p>Gustavo Petro</p><p class=" text-xs text-gray-400">Hace 10 minutos</p></div>
            </div>
            <p class=" text-lg text-red-700">Reportar</p>
        </div>
        <div class=" w-4/5 mb-8 ">
            <div>
              <img class= " my-0 mx-auto w-4/5 h-4/5  py-2  rounded-xl " src="https://apicongresovisible.uniandes.edu.co/uploads/persona/811/figura-Gustavo%20Petro-510px.jpg" alt="">
            </div>
            <div class="flex w-4/5 ">
                <div class="mx-10 flex items-center">
                  <button @click="ValueLike()" @dblclick="minutosValueLike()"><svg  class="h-8 w-8 text-red-500"  width="24" height="24" viewBox="0 0 24 24" stroke-width="2" stroke="currentColor" fill="none" stroke-linecap="round" stroke-linejoin="round">  <path stroke="none" d="M0 0h24v24H0z"/>  <path d="M12 20l-7 -7a4 4 0 0 1 6.5 -6a.9 .9 0 0 0 1 0a4 4 0 0 1 6.5 6l-7 7" /></svg></button>
                  <span v-show="notifiLike >0">{{ notifiLike }}</span>
                </div>

                <div class="flex items-center">
                  <button  @click="ValueDislike()" @dblclick="minutosValueDislike()"><svg class="h-8 w-8 text-yellow-500"  width="24" height="24" viewBox="0 0 24 24" stroke-width="2" stroke="currentColor" fill="none" stroke-linecap="round" stroke-linejoin="round">  <path stroke="none" d="M0 0h24v24H0z"/>  <circle cx="12" cy="12" r="9" />  <line x1="9" y1="10" x2="9.01" y2="10" />  <line x1="15" y1="10" x2="15.01" y2="10" />  <path d="M9.5 15.25a3.5 3.5 0 0 1 5 0" /></svg></button>
                  <span v-show="notifiDislike >0">{{ notifiDislike }}</span>
                </div>
            </div>

        </div>
        <div class=" flex justify-between w-4/5 bg-slate-300 rounded-xl p-4">
            <div><svg class="h-16 w-16 text-blue-500"  fill="none" viewBox="0 0 24 24" stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M16 7a4 4 0 11-8 0 4 4 0 018 0zM12 14a7 7 0 00-7 7h14a7 7 0 00-7-7z"/>
                  </svg>
            </div>
            <div class=" bg-white rounded-md">
              <svg class="h-16 w-16 text-blue-500"  fill="none" viewBox="0 0 24 24" stroke="currentColor">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 12l2-2m0 0l7-7 7 7M5 10v10a1 1 0 001 1h3m10-11l2 2m-2-2v10a1 1 0 01-1 1h-3m-6 0a1 1 0 001-1v-4a1 1 0 011-1h2a1 1 0 011 1v4a1 1 0 001 1m-6 0h6"/>
              </svg>

            </div>
            <div>
              <svg class="h-16 w-16 text-blue-500"  width="24" height="24" viewBox="0 0 24 24" stroke-width="2" stroke="currentColor" fill="none" stroke-linecap="round" stroke-linejoin="round">  <path stroke="none" d="M0 0h24v24H0z"/>  <circle cx="10" cy="10" r="7" />  <line x1="21" y1="21" x2="15" y2="15" /></svg>

            </div>
        </div>

      </div>
       
    </div>
</template>

<style scoped>

</style>
