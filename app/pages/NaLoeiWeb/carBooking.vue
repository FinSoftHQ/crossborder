<template>
    <UContainer>
        <section class="bg-gray-50 py-8 antialiased dark:bg-gray-900 md:py-12">
            <div class="mx-auto max-w-screen-xl px-4 2xl:px-0">
                <!-- Heading & Filters -->
                <div class="mb-4 items-end justify-between space-y-4 sm:flex sm:space-y-0 md:mb-8">
                    <div>
                        <nav class="flex"
                             aria-label="Breadcrumb">
                        </nav>
                        <h2 class="mt-3 text-xl font-semibold text-gray-900 dark:text-white sm:text-2xl">
                            รถที่พร้อมจอง
                        </h2>
                    </div>
                </div>
                <div class="mb-4 grid gap-4 sm:grid-cols-2 md:mb-8 lg:grid-cols-3 xl:grid-cols-4">
                    <div v-for="car in cars"
                         :key="car.id"
                         class="rounded-lg border border-gray-200 bg-white p-6 shadow-sm dark:border-gray-700 dark:bg-gray-800">
                        <div class="h-56 w-full">
                            <a href="#">
                                <img :src="car.imageUrl"
                                     class="mx-auto h-full dark:hidden"
                                     :alt="car.name" />
                                <img :src="car.darkImageUrl"
                                     class="mx-auto hidden h-full dark:block"
                                     :alt="car.name" />
                            </a>
                        </div>
                        <div class="pt-6">
                            <a href="#"
                               class="text-lg font-semibold leading-tight text-gray-900 hover:underline dark:text-white">{{
                                car.name }}</a>
                            <div class="mt-2 flex items-center gap-2">
                                <p class="text-sm font-medium text-gray-900 dark:text-white">{{ car.seats }}</p>
                                <p class="text-sm font-medium text-gray-500 dark:text-gray-400">({{ car.type }})
                                </p>
                            </div>
                        </div>
                        <div class="mt-4 flex items-center justify-between gap-4">
                            <p class="text-2xl font-extrabold leading-tight text-gray-900 dark:text-white">฿ {{
                                car.pricePerDay }}</p>
                            <UButton to="/booking/reservecar"
                                     class="inline-flex items-center rounded-lg bg-primary-700 px-5 py-2.5 text-sm font-medium text-white hover:bg-primary-800 focus:outline-none focus:ring-4 focus:ring-primary-300 dark:bg-primary-600 dark:hover:bg-primary-700 dark:focus:ring-primary-800">
                                จองรถ
                            </UButton>
                        </div>
                    </div>
                </div>
                <div class="w-full text-center">
                    <button type="button"
                            class="rounded-lg border border-gray-200 bg-white px-5 py-2.5 text-sm font-medium text-gray-900 hover:bg-gray-100 hover:text-primary-700 focus:z-10 focus:outline-none focus:ring-4 focus:ring-gray-100 dark:border-gray-600 dark:bg-gray-800 dark:text-gray-400 dark:hover:bg-gray-700 dark:hover:text-white dark:focus:ring-gray-700">Show
                        more</button>
                </div>
            </div>
        </section>
    </UContainer>
</template>
<script setup lang="ts">
import { ref } from 'vue';

// Define your reactive variables
const cars = ref([
    {
        id: 1,
        name: 'Toyota Corolla',
        pricePerDay: 1200,
        type: 'Sedan',
        seats: '4 Seats',
        imageUrl: 'https://example.com/images/toyota-corolla.jpg',
        darkImageUrl: 'https://example.com/images/toyota-corolla-dark.jpg',
        bestSeller: true,
    },
    {
        id: 2,
        name: 'Honda CR-V',
        pricePerDay: 2000,
        type: 'SUV',
        seats: '5 Seats',
        imageUrl: 'https://example.com/images/honda-crv.jpg',
        darkImageUrl: 'https://example.com/images/honda-crv-dark.jpg',
        fastBooking: true,
    },
    {
        id: 3,
        name: 'Mazda 2',
        pricePerDay: 900,
        type: 'Hatchback',
        seats: '4 Seats',
        imageUrl: 'https://example.com/images/mazda-2.jpg',
        darkImageUrl: 'https://example.com/images/mazda-2-dark.jpg',
        bestPrice: true,
    },
    {
        id: 4,
        name: 'Mercedes-Benz E-Class',
        pricePerDay: 5000,
        type: 'Luxury',
        seats: '4 Seats',
        imageUrl: 'https://example.com/images/mercedes-e-class.jpg',
        darkImageUrl: 'https://example.com/images/mercedes-e-class-dark.jpg',
        luxury: true,
    },
    {
        id: 5,
        name: 'Ford Ranger',
        pricePerDay: 2500,
        type: 'Pickup',
        seats: '5 Seats',
        imageUrl: 'https://example.com/images/ford-ranger.jpg',
        darkImageUrl: 'https://example.com/images/ford-ranger-dark.jpg',
        popular: true,
    },
]);
</script>
