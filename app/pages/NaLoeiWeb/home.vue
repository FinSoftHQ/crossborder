<template>
    <UContainer>
        <section class="bg-gray-50 py-8 antialiased dark:bg-gray-900 md:py-12">
            <div class="mx-auto max-w-screen-xl px-4 2xl:px-0">
                <!-- Heading -->
                <div class="mb-8 text-center">
                    <h2 class="text-3xl font-extrabold text-gray-900 dark:text-white sm:text-4xl">
                        สินค้าและบริการทั้งหมด
                    </h2>
                    <p class="mt-2 text-lg text-gray-600 dark:text-gray-400">
                    </p>
                </div>
                <!-- Product Categories -->
                <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-5 gap-6">
                    <a v-for="category in categories"
                       :key="category.id"
                       :href="category.link"
                       class="relative overflow-hidden rounded-lg border border-gray-200 bg-white shadow-md dark:border-gray-700 dark:bg-gray-800 text-center p-4 hover:bg-gray-100 dark:hover:bg-gray-700 transition">
                        <div class="flex justify-center mb-4">
                            <UIcon :name="category.iconUrl"
                                   class="w-16 h-16 text-gray-500 dark:text-gray-400" />
                        </div>
                        <h3 class="text-lg font-semibold text-gray-900 dark:text-white">
                            {{ category.name }}
                        </h3>
                    </a>
                </div>
            </div>
        </section>
    </UContainer>
</template>

<script setup lang="ts">
import { ref } from 'vue';

// Define product categories
const categories = ref([
    {
        id: 1,
        name: 'ห้องพัก',
        iconUrl: 'i-mdi-hotel',
        link: '/NaLoeiWeb/hotelBooking',
    },
    {
        id: 2,
        name: 'จองรถ',
        iconUrl: 'i-mdi-car',
        link: '/NaLoeiWeb/carBooking',
    },
    {
        id: 3,
        name: 'จองทัวร์',
        iconUrl: 'i-mdi-map',
        link: '/packageTour/home',
    },   
]);
</script>
