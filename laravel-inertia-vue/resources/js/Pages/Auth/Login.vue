<script setup>
import { useForm } from '@inertiajs/vue3';
import { route } from '../../../../vendor/tightenco/ziggy/src/js';
import TextInput from "../Components/TextInput.vue";

const form = useForm({
    email: null,
    password: null,
    remember: null,
}); 

const submit =() => {
    form.post(route('login'), {
        onError: () => form.reset('password'),
    });
}
</script>

<template>
    <!-- 0:00 /video #18 -->

    <Head title="Login" />

    <h1 class="title">
        Login to your account
    </h1>

    <div class="w-2/4 mx-auto">
        <form @submit.prevent="submit">

            <TextInput
                name="email" 
                type="email"
                v-model="form.email" 
                :message="form.errors.email"
             />

            <TextInput 
                name="password" 
                type="password"
                v-model="form.password" 
                :message="form.errors.password"
             />

            <div class="flex items-center gap-2">
                <label for="remember">Remember me</label>
                <input type="checkbox" v-model="form.remember" id="remember" />
            </div>

            <div>
                <p class="text-slate-600 mb-2">Need an account? <a class="text-link" :href="route('register')">Register</a></p>
                <button class="primary-btn">Login</button>
            </div>

        </form>
    </div>
</template>