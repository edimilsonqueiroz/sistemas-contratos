<script setup>
    import AuthenticatedLayout from '@/Layouts/AuthenticatedLayout.vue';
    import { Head } from '@inertiajs/vue3';
</script>
<script>
    export default {
        methods: {
            showAlert() {
            
                const Toast = this.$swal.mixin({
                    toast: true, 
                    position: "top", 
                    showConfirmButton: false, 
                    timer: 3000, 
                    timerProgressBar: true,
                });
                
                Toast.fire({
                    icon: "success",
                    title: "Cadastrado com sucesso!"
                });
                
            }
        },
    };
    
</script>


<template>
    <Head title="Dashboard" />

    <AuthenticatedLayout>
        <div class="py-2">
            <div class="mx-auto">
                <div
                    class="overflow-x-hidden-hidden bg-white shadow-sm sm:rounded-lg"
                >
                    <div class="p-6 text-gray-900">
                        <button @click="showAlert">Hello world</button>

                        <ModalLink href="#confirm-action">
                            Abrir Modal
                        </ModalLink>

                        <Modal name="confirm-action">
                            <h1>Modal local</h1>
                        </Modal>

                    </div>
                </div>
            </div>
        </div>
    </AuthenticatedLayout>
</template>
