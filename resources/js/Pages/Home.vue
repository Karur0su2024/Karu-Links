<script setup>



import { Head } from '@inertiajs/vue3';

const props = defineProps({
    links: Array,
});

</script>


<template>

    <Head title="Links" />

    <div class="container mx-auto my-12">
        <h1 class="text-xl font-bold">Links</h1>
        <div class="mt-6" v-if="links">
            <ul class="list-disc pl-5">
                <li v-for="link in links" :key="link.id">
                    <a :href="link.url" class="text-blue-500 hover:underline">
                        {{ link.name }}
                    </a>
                </li>
            </ul>

        </div>
        <div class="mt-6" v-else>
            Test
        </div>
    </div>
</template>
