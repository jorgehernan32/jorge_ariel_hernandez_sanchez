<template>
  <nav class="navbar bg-body-tertiary">
    <div class="container-fluid">
      <h1 class="navbar-brand">Registrate</h1>
      <div>
        <RouterLink exact-active-class="activo" class="me-2" to="/">Home</RouterLink>
        <RouterLink exact-active-class="activo" to="/tareas">Tareas</RouterLink>
        <RouterLink exact-active-class="activo" to="/registros">Registros</RouterLink>
      </div>
    </div>
  </nav>
</template>

<script setup lang="ts">
import {RouterLink} from "vue-router";

</script>

<style scoped>
.activo{
  color: black;
}
</style>