<template>
    <div>
        <router-link :to="data.path">{{ data.name }}</router-link>
    </div>
</template>

<script lang="ts" setup>
import  type IMenuItem from '@/interface/IMenuItem';
const data = defineProps<IMenuItem>;
</script>










<!-- interface ImenuItem{
    path:string;
    name:string;
}
defineProps<ImenuItem>
</ImenuItem>();
import type Imenu -->




















<!-- <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/about">About</RouterLink> -->
        <!-- <h1>Mi profe es</h1>
        <h2>
            <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/about">About</RouterLink>
        </h2> -->
       <!--  <ul>
            usuario
        
        </ul> -->