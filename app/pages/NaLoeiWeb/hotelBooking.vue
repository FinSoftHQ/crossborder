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
                            ห้องพักที่พร้อมจอง
                        </h2>
                    </div>
                </div>
                <div class="mb-4 grid gap-4 sm:grid-cols-2 md:mb-8 lg:grid-cols-3 xl:grid-cols-4">
                    <div v-for="room in rooms"
                         :key="room.id"
                         class="rounded-lg border border-gray-200 bg-white p-6 shadow-sm dark:border-gray-700 dark:bg-gray-800">
                        <div class="h-56 w-full">
                            <a href="#">
                                <img :src="room.imageUrl"
                                     class="mx-auto h-full dark:hidden"
                                     :alt="room.name" />
                                <img :src="room.darkImageUrl"
                                     class="mx-auto hidden h-full dark:block"
                                     :alt="room.name" />
                            </a>
                        </div>
                        <div class="pt-6">
                            <a href="#"
                               class="text-lg font-semibold leading-tight text-gray-900 hover:underline dark:text-white">{{
                                room.name }}</a>
                            <div class="mt-2 flex items-center gap-2">
                                <p class="text-sm font-medium text-gray-900 dark:text-white">{{ room.capacity }}</p>
                                <p class="text-sm font-medium text-gray-500 dark:text-gray-400">({{ room.type }})
                                </p>
                            </div>
                        </div>
                        <div class="mt-4 flex items-center justify-between gap-4">
                            <p class="text-2xl font-extrabold leading-tight text-gray-900 dark:text-white">฿ {{
                                room.pricePerNight }}</p>
                            <UButton to="/booking/reserveroom"
                                     class="inline-flex items-center rounded-lg bg-primary-700 px-5 py-2.5 text-sm font-medium text-white hover:bg-primary-800 focus:outline-none focus:ring-4 focus:ring-primary-300 dark:bg-primary-600 dark:hover:bg-primary-700 dark:focus:ring-primary-800">  
                                จองห้องพัก
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
const rooms = ref([
    {
        id: 1,
        name: 'Deluxe Room',
        pricePerNight: 1500,
        type: 'Double Bed',
        capacity: '2 Adults',
        imageUrl: 'https://example.com/images/deluxe-room.jpg',
        darkImageUrl: 'https://example.com/images/deluxe-room-dark.jpg',
        bestSeller: true,
    },
    {
        id: 2,
        name: 'Family Suite',
        pricePerNight: 3000,
        type: 'Family',
        capacity: '4 Adults',
        imageUrl: 'https://example.com/images/family-suite.jpg',
        darkImageUrl: 'https://example.com/images/family-suite-dark.jpg',
        fastBooking: true,
    },
    {
        id: 3,
        name: 'Single Room',
        pricePerNight: 800,
        type: 'Single Bed',
        capacity: '1 Adult',
        imageUrl: 'https://example.com/images/single-room.jpg',
        darkImageUrl: 'https://example.com/images/single-room-dark.jpg',
        bestPrice: true,
    },
    {
        id: 4,
        name: 'Executive Suite',
        pricePerNight: 5000,
        type: 'Suite',
        capacity: '2 Adults',
        imageUrl: 'https://example.com/images/executive-suite.jpg',
        darkImageUrl: 'https://example.com/images/executive-suite-dark.jpg',
        luxury: true,
    },
    {
        id: 5,
        name: 'Standard Room',
        pricePerNight: 1000,
        type: 'Double Bed',
        capacity: '2 Adults',
        imageUrl: 'https://example.com/images/standard-room.jpg',
        darkImageUrl: 'https://example.com/images/standard-room-dark.jpg',
        popular: true,
    },
]);
</script>
