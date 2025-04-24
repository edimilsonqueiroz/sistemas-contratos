<script setup>
    import AuthenticatedLayout from '@/Layouts/AuthenticatedLayout.vue';
    import { Head } from '@inertiajs/vue3';
    
    const show = () => {
        this.$swal.fire({
            toast: true, 
            title: "Cadastrado com sucesso!",
            icon: "success",
            position: "top", 
            showConfirmButton: false, 
            timer: 3000, 
            timerProgressBar: false,
        });
    }
</script>
<script>

    export default {
        methods: {
            alert(){
                this.$swal.fire({
                    toast: true, 
                    title: "Cadastrado com sucesso!",
                    icon: "success",
                    position: "top", 
                    showConfirmButton: false, 
                    timer: 3000, 
                    timerProgressBar: true,
                });
            }
        }
    }

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
                        <button @click="alert">Usuários</button>
                        <button @click="alert">Alerta</button>
                    </div>
                </div>
            </div>
        </div>
    </AuthenticatedLayout>
</template>
