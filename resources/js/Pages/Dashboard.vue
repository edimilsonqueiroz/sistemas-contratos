<script setup>
    import AuthenticatedLayout from '@/Layouts/AuthenticatedLayout.vue';
    import { Head } from '@inertiajs/vue3';
    
    defineProps({page: String})
</script>
<script>
  import { Bar } from 'vue-chartjs'
  import { Chart as ChartJS, Title, Tooltip, Legend, BarElement, CategoryScale, LinearScale } from 'chart.js'

  ChartJS.register(Title, Tooltip, Legend, BarElement, CategoryScale, LinearScale)

    export default {
        components: {Bar},
        data() {
            let janeiro = 20;
            let fevereiro = 40;
            let marco = 25;
            return {
                chartData: {
                    labels: [ 'Janeiro', 'Fevereiro', 'Março' ],
                    datasets: [ { data: [janeiro, fevereiro, marco] } ]
                },
                chartOptions: {
                    responsive: true,
                    maintainAspectRatio: false
                }
            }
        },

        methods: {
            alert(tipo, mensagem){
                this.$swal.fire({
                    toast:true,
                    position:"top",
                    icon: tipo,
                    showConfirmButton:false,
                    timer:3000,
                    width:400,
                    timerProgressBar:true,
                    title: mensagem
                });
            },


            showAlert(){
                this.alert("success", "Usuário cadastrado(a) com sucesso!");
            }
            
        },


    };
    
</script>


<template>
    <Head title="Dashboard" />

    <AuthenticatedLayout>
        <div class="py-2">
            <div class="mx-auto">
                <div class="overflow-x-hidden-hidden bg-white shadow-sm sm:rounded-lg">
                    <div class="p-6 text-gray-900">
                        <Bar
                            id="my-chart-id"
                            :options="chartOptions"
                            :data="chartData"
                        />
                    </div>
                    <div>
                        {{ page }}
                    </div>
                </div>
            </div>
        </div>
    </AuthenticatedLayout>
</template>
