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
            <div class="max-w-7xl mx-auto sm:px-6 lg:px-8 py-20">
                <h1 class="text-8xl font-sans font-bold text-white">WELCOME</h1>
                <p class="font-sans pt-6 text-white text-xl">This is a SPA (Single Page Applications) of notes where you can Create, Edit, Delete and Search notes made by yourself in an easy and fast way; this project was made with laravel 9 + inertia,
                    <a href="https://vuejs.org/" class="hover:text-green-900">vue.js 3</a>  and
                    <a href="https://tailwindcss.com/" class="hover:text-blue-900">tailwind CSS</a>
                </p>
            </div>
        </div>
    </AppLayout>
</template>
