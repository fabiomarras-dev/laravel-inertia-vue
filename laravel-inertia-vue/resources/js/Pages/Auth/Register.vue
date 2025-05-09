<script setup>
import Layout from '../../Layouts/Layout.vue';

defineOptions({ layout: Layout});
</script>

<template>
    <Head title="Register" />

    <h1 class="title">
        Register a new account
    </h1>

    <div class="w-2/4 mx-auto">
        <form>

            <div class="mb-6">
                <label>Name</label>
                <input type="text" />
            </div>

            <div class="mb-6">
                <label>Email</label>
                <input type="text" />
            </div>

            <div class="mb-6">
                <label>Password</label>
                <input type="password" />
            </div>

            <div class="mb-6">
                <label>Confirm Password</label>
                <input type="password" />
            </div>

        </form>
    </div>
</template>