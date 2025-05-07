<script setup>
import Layout from '../Layouts/Layout.vue';
defineOptions({ layout: Layout});

    defineProps({
        user: String
    })
</script>

<template>
    <div>
        <h1 class="text-3xl font-bold underline">About {{ user }}</h1>
    </div>
</template>

