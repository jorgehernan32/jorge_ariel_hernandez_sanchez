<template>
    <div>
        <MenuItem v-for="routes in routerView" :name="routes.name" :path ="routes.path"></MenuItem>
    </div>
</template>

<script lang="ts" setup>
import type IMenuItem from '@/interface/IMenuItem';
import MenuItem from './MenuItem.vue';
import router from '@/router';

const routeViews = router.options.routes.filter(route =>{
    return route;/* {name:router.name, path: route.path} */
}) as  IMenuItem[];
</script>