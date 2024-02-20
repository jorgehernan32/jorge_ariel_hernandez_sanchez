<template>
    <div>
        <button @click="click">click</button>
        <button @click="mostrarNombre">soy</button>
        <PostItem
        @-say-hi="click($event)"
        @nombre="mostrarNombre($event)"
        v-bind="post"
        v-for ="(post,index) in PostData" :key="index"/>
    </div>
</template>

<script setup lang="ts">
import PostData from '../../data/PostData'
import PostItem from './postitem.vue';

const click = (event: any) => {
    alert('Desde el padre ' + event)
}

const mostrarNombre = (event: any) => {
    alert('Desde el hijo: ' + event)
}

</script>

<style>
</style>
