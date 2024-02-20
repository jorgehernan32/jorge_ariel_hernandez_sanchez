<template lang="">
    <div class="card">
        <!-- 
            menu
            datos computados
            
         -->
        <span>
            <h4>id: {{props.id}} </h4>
            <h4>title: {{props.date}}</h4>
        </span>
        <h1>body: {{props.title}}</h1>
        <h1>date: {{props.body}}</h1>
        <button @click="clicked"> clickclick</button>
        <button @click="miNombre"> clickclick</button>
        <!-- <input type="text" v-model ="titulo"> -->
        <!-- <input @input="" type="number" v-model="valor">
        <input type="number" v-model="valor2">
        <h1>{{ validation}}</h1> -->
        <!-- dc toman como dependencia un valor y el estado de otro valor -->
    </div>
</template>
<!-- los gestores de estado global
    piña es un gestor de estado global vueEX
    composition
    ciclo de vida
     arrys
     sniper
    MENUCOMPONENT

-->
<script lang="ts" setup>
import { ref, computed } from 'vue'
import type { IPost } from '@/interface/IPost';
const valor = ref(0)
const valor2 = ref(0)

const validation = computed (()=> (valor.value * valor2.value) > 100)

const props = defineProps<IPost>()
const emits = defineEmits(['SayHi','Nombre'])

const nombre = 'Jorge Ariel Hernández Sánchez'
//const titulo = ref('')
//const copia = props;
//Funciones
/* EMITIS PARA UN COMPONENTES SON ACCIONES DEL HIJO */
/* const pros = defineProps<Ipost>(); */
const clicked = () => {
    /* console.log('Botón clickeado'); */
    emits("SayHi", "Desde el hijo", 'Jorge Ariel Hernández Sánchez','esta presente')
}
const miNombre = () => {
    emits('Nombre',nombre)
}
</script>

<style scoped>
.card{
    border: 1px solid rgb(100, 27, 27);
    padding: 10px;
    margin: 5px;
}
</style>