<script setup>
import { ref, watch } from "vue";
import PaginationLinks from "./Components/PaginationLinks.vue"
import { router } from "@inertiajs/vue3";
import { debounce } from "lodash";

const props = defineProps({
    users: Object,
    searchTerm: String
});

const search = ref(props.searchTerm);

watch(search, debounce((q) => router.get('/', { search: q }, { preserveState: true }),
    300
)); 

// fixing date showcase
const getDate = (date) => new Date(date).toLocaleDateString("en-us", {
    year: "numeric",
    month: "long",
    day: "numeric",
});

</script>

<template>
    <Head :title="$page.component" />
    <div class="flex justify-end mb-4">
        <div class="w-1/4">
            <input type="search" placeholder="Search" v-model="search">
        </div>
    </div>
    

        <div>
            <table class="bg-slate-300">
                <thead>
                    <tr>
                        <th>Avatar</th>
                        <th>Name</th>
                        <th>Email</th>
                        <th>Registration Date</th>
                    </tr>
                </thead>

                <tbody>
                    <tr v-for="user in users.data" :key="user.id">
                        <td>
                            <img class="avatar" :src="user.avatar ? ('storage/' + user.avatar) : ('storage/avatars/default.png')">
                        </td>
                        <td>{{ user.name }}</td>
                        <td>{{ user.email }}</td>
                        <td>{{ getDate(user.created_at) }}</td>
                    </tr>
                </tbody>

                <div>
                    <!--
                    <Link
                    v-for="link in users.links"
                    :key="link.label"
                    v-html="link.label"
                    :href="link.url" 
                    class="p-1 mx-1"
                    ></Link>
                    -->

                    <a href=""></a>
                </div>
            </table>

             <PaginationLinks :paginator="users"/>
             
        </div>
</template>

