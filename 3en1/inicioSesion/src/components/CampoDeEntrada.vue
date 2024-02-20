<!-- CampoDeEntrada.vue -->
<template>
    <div>
      <label :for="name">{{ label }}</label>
      <input :type="type" :id="name" v-model="value">
    </div>
  </template>
  
  <script>
  export default {
    props: ['name', 'label', 'type', 'value']
  }
  </script>