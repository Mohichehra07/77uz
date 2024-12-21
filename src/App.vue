<script setup>
import defoult from "./layouts/defoult.vue";
import empty from "./layouts/empty.vue";
import { useRoute } from "vue-router";
import { RouterView } from "vue-router";

const layouts = {
    empty: empty,
    defoult: defoult,
};

const route = useRoute();

</script>
<template>
    <div class="flex flex-col min-h-screen bg-white">
        <comment :is="layouts[route.meta.layout]">
            <router-view></router-view>
        </comment>
    </div>
</template>
