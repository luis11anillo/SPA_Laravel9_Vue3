<script>
import AppLayout from '@/Layouts/AppLayout.vue';

export default {
    components: {
        AppLayout,
    },
    props: {
        note: Object,
    },
    data () {
    return {
        form: {
            excerpt: this.note.excerpt,
            content: this.note.content,
            }
        }
    },
    methods: {
        submit() {
            this.$inertia.put(this.route('notes.update', this.note.id), this.form)
        },
        destroy() {
            if (confirm('¿Desea eliminar?')) {
                this.$inertia.delete(this.route('notes.destroy', this.note.id))
            }
        }
    }
}

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
                            <h3 class="text-lg text-white font-semibold">Editar una notas</h3>
                            <p class="text-sm text-gray-100">S&iacute; editas no podr&aacute;s volver al estado anterior</p>
                        </div>
                    </div>
                    <div class="md:col-span-2 mt-5 md:mt-0">
                        <div class="shadow bg-white md:rounded-md p-4">
                            <form @submit.prevent="submit">
                                <label class="block font-medium text-sm text-gray-700 pb-2">
                                    Resumen
                                </label>
                                <textarea
                                    class="form-input w-full rounded-md shadow-sm"
                                    v-model="form.excerpt" >
                                </textarea>
                                <label class="block font-medium text-sm text-gray-700 py-2">
                                    Contenido
                                </label>
                                <textarea
                                    class="form-input w-full rounded-md shadow-sm"
                                    v-model="form.content"
                                    rows="8">
                                </textarea>

                                <button class="bg-blue-800 hover:bg-blue-600 text-white font-bold py-2 px-4 rounded-md">
                                    Editar
                                </button>

                                <inertia-link
                                    :href="route('notes.index')"
                                    class="bg-amber-500 hover:bg-amber-400 text-white font-bold py-2 px-4 ml-4 rounded-md">
                                    Descartar
                                </inertia-link>

                                <hr class="my-6">

                                <a href="#" @click.prevent="destroy" class="hover:text-red-800 hover:underline">
                                    Eliminar nota
                                </a>
                            </form>

                        </div>
                    </div>
                </div>
            </div>
        </div>
    </AppLayout>
</template>
