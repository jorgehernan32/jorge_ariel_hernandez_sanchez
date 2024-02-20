<!-- Formulario.vue -->
<template>
    <form @submit.prevent="handleSubmit">
      <campo-de-entrada name="nombre" label="Nombre:" type="text" :value="formData.nombre" />
      <!-- <campo-de-entrada name="apellidoPaterno" label="ApellidoPaterno:" type="text" :value="formData.apellidoPaterno"/> -->
      <campo-de-entrada name="email" label="Email:" type="email" :value="formData.email" />
      <campo-de-entrada name="mensaje" label="Mensaje:" type="text" :value="formData.mensaje" />
      <button type="submit">Enviar</button>
    </form>
  </template>
  
  <script>
  import CampoDeEntrada from './CampoDeEntrada.vue'
  
  export default {
    components: {
      CampoDeEntrada
    },
    data() {
      return {
        formData: {
          nombre: '',
          /* apellidoPaterno:'', */
          email: '',
          mensaje: ''
        }
      }
    },
    methods: {
      handleSubmit() {
        // Aquí puedes enviar los datos del formulario a un servidor
        console.log('Datos del formulario:', this.formData);
        // Por ahora, solo limpiamos los datos del formulario
        this.formData.nombre = '';
        /* this.formData.apellidoPaterno = ''; */
        this.formData.email = '';
        this.formData.mensaje = '';
      }
    }
  }
  </script>
  