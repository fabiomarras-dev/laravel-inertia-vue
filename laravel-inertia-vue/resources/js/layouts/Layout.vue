<script setup>
import { Link } from '@inertiajs/vue3';
</script>



<template>
    <div>
        <header class="bg-indigo-500 text-white">
            <nav class="flex item-center justify-between p-4 max-w-scren-lg mx-auto">
                <div>
                    <Link href="/">Home</Link>
                    <Link href="/about">About</Link>
                </div>
            </nav>
        </header>
        <main class="p-4">
            <slot></slot>
        </main>
    </div>
</template>