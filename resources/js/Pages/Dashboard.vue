<script setup>
import AppLayout from '@/Layouts/AppLayout.vue';
//import Welcome from '@/Components/Welcome.vue';
</script>

<template>
    <AppLayout title="Dashboard">
        <template #header>
            <h2 class="font-semibold text-xl text-white leading-tight">
                Dashboard
            </h2>
        </template>

        <div class="py-12">
            <div class="max-w-7xl mx-auto sm:px-6 lg:px-8">
                <h1 class="text-8xl font-sans font-bold text-orange-700">WELCOME</h1>
                <p class="font-sans pt-6 text-white">This is a SPA (Single Page Applications) of notes where you can Create, Edit, Delete and Search notes made by yourself, this project was made with laravel 9 + inertia,
                    <a href="https://vuejs.org/">vue.js 3</a>  and
                    <a href="https://tailwindcss.com/">tailwind CSS</a>
                </p>
            </div>
        </div>
    </AppLayout>
</template>
