<script setup>
import Layout from '../Layouts/Layout.vue';

defineOptions({ layout: Layout});
</script>

<template>
    <Head :title="$page.component" />
        <div>
            <h1>{{ $page.component }}</h1>
        </div>
</template>

