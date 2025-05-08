<script setup>
import Layout from '../Layouts/Layout.vue';

defineOptions({ layout: Layout});
</script>

<template>
    <Head :title="$page.component" />
        <div>
            <h1 class="text-3xl font-bold underline">{{ $page.component }}</h1>
        </div>
</template>

