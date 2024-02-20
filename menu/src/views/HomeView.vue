<script setup lang="ts">
import { Ref } from 'vue';

const nombre = ref('');
const error = ref(true);
const error = ref('#d03');

if(nombre.value.length < 5){
  error.value = false
}

if(nombre.value.length < 5){
  error.value = false
}
</script>

<template>
  <main>
    <h2> This is Home!</h2>
    <h3>MY NAME IS
    <input :input="checkvalitacion" type="text" v-model="nombre">
    <h1 :style="{'color':error}">{{ nombre }}</h1>
      <h1 :class="{'error':error}">
        nombre
      </h1>
    </h3>
  </main>
</template>

<style>
.error{
  color: red;
}
h1{
background-color:  red;

}
</style>


