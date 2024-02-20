<template>
  <div class="container">
    <button 
      @click="irAlFormulario"
      class="btn btn-success my-2">Agregar</button>
    <Tabla />
  </div>
</template>

<script setup lang="ts">
import RegistroTabla from "@/components/RegistroTabla.vue";
import {useRouter} from "vue-router";

const router = useRouter();
const irAlFormulario = ()=>{
  router.push('/Registro-formulario')
}
</script>

<style scoped>

</style>