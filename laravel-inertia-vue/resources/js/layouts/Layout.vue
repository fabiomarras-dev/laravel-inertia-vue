<script setup>
import { Link } from '@inertiajs/vue3';
import { route } from '../../../vendor/tightenco/ziggy/src/js';
</script>



<template>
    <div>
        <header class="bg-indigo-500 text-white">
            <nav class="flex item-center justify-between p-4 max-w-scren-lg mx-auto">
                <div>
                    <Link :href="route('home')">Home</Link>
                    <Link :href="route('about')">About</Link>
                </div>
            </nav>
        </header>
        <main class="p-4">
            <slot></slot>
        </main>
    </div>
</template>