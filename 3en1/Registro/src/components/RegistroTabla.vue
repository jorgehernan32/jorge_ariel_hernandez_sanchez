<template>
    <div class="card">
      <table class="table">
      <thead>
        <tr>
          <th scope="col">Nombre</th>
          <th scope="col">Correo</th>
          <th scope="col">Estado</th>
          <th scope="col">Acciones</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="registro in registros" :key="registro._id">
          <td>{{ registro.name }}</td>
          <td>{{ registro.correo }}</td>
          <td>
            {{ registro.status ? 'pendiente':'realizada' }}
          </td>
          <td>
            <button>
            <span @click="editar(registro._id)" class="icono">
                Editar🚼
            </span>
          </button>
          <button>
            <span 
              @click="eliminar(registro)"
              class="icono">
              Eliminar🚮
            </span>
          </button>
            
          </td>
        </tr>
      </tbody>
      </table>
    </div>
  </template>
  
  <script setup lang="ts">
  import {onMounted, ref} from "vue";
  import {API,Iregistro} from "@/contantes";
  import {useRouter} from "vue-router";
  
  const registros = ref<Iregistro[]>([])
  const router = useRouter();
  
  const editar = (id:string)=>{
    router.push(`/registro-formulario/${id}`)
  }
  
  const eliminar = async({name, _id}:Iregistro)=>{
    const respuesta = confirm(`¿Estas segudo de eliminar a ${name}?`)
    if(respuesta){
      const data = await fetch(`${API}/api/task/${_id}`,{
        method:'DELETE'
      })
      const registro = await data.json()
      if(registro){
        registros.value = registros.value.filter(x => x._id !== _id)
      }
    }
  }
  onMounted(async()=>{
    const data = await fetch(`${API}/api/task`)
    registros.value = await data.json()
  })
  </script>
  
  <style scoped>
  .icono{
    cursor: pointer;
  }
  </style>