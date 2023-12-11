<script setup>

const props = defineProps({ id:{
    type: Number,

},
    nombre:{
        type: String,
        default: 'andres'
    },
    mensaje: {
        type: String,
        defaul: 'hola'
    }

})

const emits = defineEmits('ShowMensaje')
function ShowMensaje(){
    emits('ShowMensaje', props.id)
}
</script>

<template >
 
    <div class="  my-0 mx-auto mt-4 w-3/4 bg-gray-500 flex justify-around items-center " @click="ShowMensaje">
    
        <div>
            imagen
        </div>
        <div class="">
            <p>{{ props.nombre }}</p>
            <p class=" text-xs text-gray-200">Hace 10 minutos</p>
        </div>
    </div>
 

</template>