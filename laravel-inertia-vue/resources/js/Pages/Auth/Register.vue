<script setup>
//import { reactive } from 'vue';
//import { router } from '@inertiajs/vue3';
import { useForm } from '@inertiajs/vue3';
import { route } from '../../../../vendor/tightenco/ziggy/src/js';
import TextInput from "../Components/TextInput.vue";

/* const form = reactive({
    name: null,
    email: null,
    password: null,
    password_confirmation: null,
}); */

const form = useForm({
    name: null,
    email: null,
    password: null,
    password_confirmation: null,
}); 

const submit =() => {
    //console.log(form);
    //router.post('/register', form);

    form.post(route('register'), {
        onError: () => form.reset('password', 'password_confirmation'),
    });
}
</script>

<template>
    <Head title="Register" />

    <h1 class="title">
        Register a new account
    </h1>

    <div class="w-2/4 mx-auto">
        <form @submit.prevent="submit">

            <TextInput 
                name="name" 
                v-model="form.name" 
                :message="form.errors.name"
             />

            <!-- <div class="mb-6">
                <label>Name</label>
                <input type="text" v-model="form.name"/>
                <small>{{ form.errors.name }}</small>
            </div> -->

            <TextInput 
                name="email" 
                type="email"
                v-model="form.email" 
                :message="form.errors.email"
             />

            <!-- <div class="mb-6">
                <label>Email</label>
                <input type="text" v-model="form.email"/>
                <small>{{ form.errors.email }}</small>
            </div> -->

            <TextInput 
                name="password" 
                type="password"
                v-model="form.password" 
                :message="form.errors.password"
             />

            <!-- <div class="mb-6">
                <label>Password</label>
                <input type="password" v-model="form.password"/>
                <small>{{ form.errors.password }}</small>
            </div> -->

            <TextInput 
                name="confirm password" 
                type="password"
                v-model="form.name" 
             />

            <!-- <div class="mb-6">
                <label>Confirm Password</label>
                <input type="password" v-model="form.password_confirmation" />
            </div> -->




            <div>
                <p class="text-slate-600 mb-2">Already a user? <a class="text-link">Login</a></p>
                <button class="primary-btn">Register</button>
            </div>

        </form>
    </div>
</template>