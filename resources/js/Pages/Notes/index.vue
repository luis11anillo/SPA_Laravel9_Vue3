<script>
import AppLayout from '@/Layouts/AppLayout.vue';

export default {
    components: {
        AppLayout,
    },
    props: {
        notes: Array
    },
    data () {
        return {
            q: ''
        }
    },
    watch: {
        q: function(value) {
            this.$inertia.replace(this.route('notes.index', {q: value}))
        }
    }
}

</script>

<template>
    <AppLayout title="index">
        <template #header>
            <h2 class="font-semibold text-xl text-white leading-tight">
                M&oacute;dulo de notas
            </h2>
        </template>

        <div class="py-12">
            <div class="max-w-6xl mx-auto sm:-6px lg:px-8">
                <div class="md:grid md:grid-cols-3 md:gap-6">
                    <div class="md:col-span-3">
                        <div class="px-4 sm:px0">
                            <h2 class="text-2xl text-center text-white text-semibold">Listado de notas</h2>
                            <p class="text-sm text-center text-white">Toma el registro correcto y ejecuta cualquier funci&oacute;n (Ver, Editar o Eliminar)</p>
                        </div>
                    </div>
                    <div class="md:col-span-3 mt-5 md:mt-0">
                        <div class="shadow bg-white md:rounded-md p-4">

                            <!-- Buscador y btn crear -->
                            <div class="flex justify-between">
                                <input type="text" class="form-imput rounded-full shadow-sm w-4/5" placeholder="Buscar" v-model="q">
                                <inertia-link
                                    class="bg-blue-500 hover:bg-blue-600 text-white text-bold px-4 py-2 rounded-full"
                                    :href="route('notes.create')">
                                    +
                                </inertia-link>
                            </div>

                            <hr class="my-4">

                            <!-- Tabla -->
                            <table>
                                <tr v-for="note in notes" >
                                    <td class="border px-4 py-2">
                                        {{ note.excerpt }}
                                    </td>
                                    <td class="px-4 py-2 hover:bg-blue-100">
                                        <inertia-link :href="route('notes.show', note.id)">
                                            Ver
                                        </inertia-link>
                                    </td>
                                    <td class="px-4 py-2 hover:bg-yellow-100 rounded-r-lg">
                                        <inertia-link :href="route('notes.edit', note.id)">
                                            Editar
                                        </inertia-link>
                                    </td>
                                </tr>
                            </table>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </AppLayout>
</template>
