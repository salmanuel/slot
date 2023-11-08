<script setup>
import AuthenticatedLayout from '@/Layouts/AuthenticatedLayout.vue';
import Card from '@/Components/Card.vue';
import { Head } from '@inertiajs/vue3';


const comp_accessories = [
    {
        id: 1,
        name: 'Headphone',
        thumbnail: 'https://www.sony.com.ph/image/8f499d4640b363762e66edd1a4916a10?fmt=pjpeg&bgcolor=FFFFFF&bgc=FFFFFF&wid=2515&hei=1320',
        price: '7,499.00 Php'
    },
    {
        id: 2,
        name: 'Mouse',
        thumbnail: 'https://www.officewarehouse.com.ph/__resources/_web_data_/products/products/images/6676.jpg',
        price: '415.00 Php'
    },
];
</script>

<template>
    <Head title="Dashboard" />

    <AuthenticatedLayout>
        <template #header>
            <h2 class="font-semibold text-xl text-gray-800 leading-tight">Dashboard</h2>
        </template>

        <div class="py-12">
            <div class="max-w-7xl mx-auto sm:px-6 lg:px-8">
                <div class="bg-gray-200 flex justify-between overflow-hidden shadow-sm sm:rounded-lg">
                    <div class="grid">
                        <div v-for="comp_accessory in comp_accessories" :key="comp_accessory.id">
                            <Card>
                                    <template v-slot:header>
                                        <h1 class="2xl">{{ comp_accessory.name }}</h1>
                                    </template>
                                    <template v-slot:content>
                                        <div>
                                            <img :src="comp_accessory.thumbnail" alt="">
                                        </div>
                                    </template>
                            </Card>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <Card>
            <template v-slot:header>
                <h3>Header</h3>
            </template>
            <template v-slot:default>
                <img src="https://www.seiu1000.org/sites/main/files/main-images/camera_lense_0.jpeg" alt="" style="width:350px; height:200px;">
            </template>
            <template v-slot:footer>
                <button class="p-2 rounded shadow-md hover:bg-gray-900 hover:text-white">Aur Naur</button>
            </template>
        </Card>
    </AuthenticatedLayout>
</template>

<style scoped>
.grid{
    display: grid;
    grid-template-columns: repeat(3,1fr);
    gap: 24px 24px;
}

</style>
