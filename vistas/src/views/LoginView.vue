<template>
    <div>
        <div class="">
            <label for="">Email:</label>
            <input v-model="email" type="text">
        </div>
        <div class="">
            <label for="">password</label>
            <input v-on="" v-model="password" type="pasword" name="" id="">
        </div>
        <butto v-bind="" :disabled="error">Login</butto> <!-- !(email.value.length>0 && password.value.length>0) -->
        <hr/>
        {{ email }}
        {{ password }}
    </div>
</template>

<script lang="" setup>
import { ref, 
    onMounted(() => {
    console.log("antes de crear")
})
 onBeforeMount(() => {
    console.log("montado")
}) } from "vue"
import type { Ref } from "vue"
/* la constante email se debe de declarar el tipo de valor que es, se toma el tipo de string hasta que se le asigna  */
/* solamente string */
const email:Ref<string>= ref('')/* valores primirivos el Ref */
const password:Ref<string>=ref('')
const error: Ref<boolean> = ref(true)

const checkValidation = ()=>{
    console.log('ejecutando')
    error.value = true
    return (email.value.length>0 && password.value.length){
        error.value = false;
    }
}
</script>

<!-- <script>
import {defineComponent} from 'vue'

defineComponent({
    data(){
        return{}
    },
    setup(props){},

    defineComponent({
        setup(this.props.){

        }
    })
})
 -->
<style scoped></style>

