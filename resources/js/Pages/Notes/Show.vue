<script setup>
import AppLayout from '@/Layouts/AppLayout.vue';

defineProps({
    note: Object,
});

</script>

<template>
    <AppLayout title="Dashboard">
        <template #header>
            <h2 class="font-semibold text-xl text-white leading-tight">
                M&oacute;dulo de notas
            </h2>
        </template>

        <div class="py-12">
            <div class="max-w-7xl mx-auto sm:px-6 lg:px-8">
                <div class="md:grid md:grid-cols-3 md:gap-6">
                    <div class="md:col-span-1">
                        <div class="px-4 sm:px0">
                            <h3 class="text-lg text-white font-semibold">Detalles de una notas</h3>
                            <p class="text-sm text-gray-100 pt-4">{{ note.excerpt }}</p>
                        </div>
                    </div>
                    <div class="md:col-span-2 mt-5 md:mt-0">
                        <div class="shadow bg-white md:rounded-md p-4 text-justify">
                            <p>{{ note.content }}</p>

                            <hr class="my-6">

                            <inertia-link
                                :href="route('notes.index')"
                                class="hover:bg-gray-200 p-2 rounded">
                                Volver
                            </inertia-link>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </AppLayout>
</template>
