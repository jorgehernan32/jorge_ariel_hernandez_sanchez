<template>
    <div class="card mx-auto mt-5" style="width: 350px;">
      <form 
        @submit.prevent="procesarFormulario"
        class="card-body">
        <h1>{{ registro ? 'Editar':'Agregar' }} Registro</h1>
        <input 
          class="form-control mb-2"
          type="text" 
          v-model="formData.nombre"
          placeholder="Nombre"
          required>
        <input 
          type="text"
          placeholder="Descripción"
          v-model="formData.correo"
          class="form-control mb-3"
          required
          >
        <button :disabled="cargando" class="btn btn-primary w-100">Guardar</button>
      </form>
    </div>
  </template>
  
  <script setup lang="ts">
  import {computed, onMounted, reactive, ref, watch} from "vue";
  import {API, IRegistro} from "@/contantes";
  import {useRouter} from "vue-router";
  
  const props = defineProps({
    registro:{
      type: Object as ()=> IRegistro | null,
      default: null
    }
  })
  const formData = reactive({
    nombre: '',
    correo: ''
  })
  const cargando = ref(false)
  const router = useRouter()
  const registro = computed(()=> props.registro)
  
  watch(registro, ()=>{
    formData.nombre = registro.value.name
    formData.correo = registro.value.description
  })
  
  const procesarFormulario = async()=>{
    cargando.value = true;
    if(registro.value){
      await fetch(`${API}/api/task/${registro.value._id}`,{
        method: 'PATCH',
        body: JSON.stringify({name:formData.nombre, description: formData.correo}),
        headers:{
          'Content-Type': 'application/json'
        }
      })
    }else{
      await fetch(`${API}/api/task`,{
        method: 'POST',
        body: JSON.stringify({name:formData.nombre, description: formData.correo}),
        headers:{
          'Content-Type': 'application/json'
        }
      })
    }
    cargando.value = false;
    router.back()
  }
  </script>
  
  <style scoped>
  
  </style>