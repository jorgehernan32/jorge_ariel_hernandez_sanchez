<template>
  <div class="container">
    <Formulario
      :registro="registro"
    />
  </div>
</template>

<script setup lang="ts">
import RegistroFormulario from '@/components/RegistroFormulario.vue';
import { API, IRegistro } from '@/contantes';
import { onBeforeMount, ref } from 'vue';
import {useRoute} from "vue-router";

const {params} = useRoute()
const registro = ref<null | IRegistro>(null)

onBeforeMount(async()=>{
  if(params.id){
    const data = await fetch(`${API}/api/task/${params.id}`)
    registro.value = await data.json()
  }
})
</script>

<style scoped>

</style>