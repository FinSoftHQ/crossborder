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
        name: 'Zhong Tong Single Decker',
        pricePerDay: 7000, // Adjusted price
        type: 'Bus',
        seats: '40 Seats',
        imageUrl: 'https://www.thanatwit.com/wp-content/uploads/2022/07/bus-5-1.jpg',
        darkImageUrl: 'https://www.thanatwit.com/wp-content/uploads/2022/07/bus-5-1.jpg',
        bestSeller: true,
        registrationNumber: 'BUS-1234',
    },
    {
        id: 2,
        name: 'Single Decker Coach',
        pricePerDay: 9000, // Adjusted price
        type: 'Coach',
        seats: '45 Seats',
        imageUrl: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQfJjNpoeGZt17DvcNROPl0mig6JvCC_OEYhQ&s',
        darkImageUrl: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQfJjNpoeGZt17DvcNROPl0mig6JvCC_OEYhQ&s',
        fastBooking: true,
        registrationNumber: 'COACH-5678',
    },
    {
        id: 3,
        name: 'Standard Double Decker',
        pricePerDay: 11000, // Adjusted price
        type: 'Tour Bus',
        seats: '50 Seats',
        imageUrl: 'https://image.travelcatteralls.co.uk/images/tbs/Image%20Grid/img_8301.jpeg',
        darkImageUrl: 'https://image.travelcatteralls.co.uk/images/tbs/Image%20Grid/img_8301.jpeg',
        bestPrice: true,
        registrationNumber: 'TOUR-9012',
    },
    {
        id: 4,
        name: 'Platinum Double Decker',
        pricePerDay: 14000, // Adjusted price
        type: 'Luxury Coach',
        seats: '55 Seats',
        imageUrl: 'https://www.thanatwit.com/wp-content/uploads/2022/07/bus-3-2.jpg',
        darkImageUrl: 'https://www.thanatwit.com/wp-content/uploads/2022/07/bus-3-2.jpg',
        luxury: true,
        registrationNumber: 'LUX-3456',
    },
    {
        id: 5,
        name: 'Euro 13.8 Single Decker',
        pricePerDay: 13000, // Adjusted price
        type: 'Imported Coach',
        seats: '50 Seats',
        imageUrl: 'https://www.thanatwit.com/wp-content/uploads/2022/07/bus-4-2.jpg',
        darkImageUrl: 'https://www.thanatwit.com/wp-content/uploads/2022/07/bus-4-2.jpg',
        popular: true,
        registrationNumber: 'EURO-7890',
    },
    {
        id: 6,
        name: 'Premium Van',
        pricePerDay: 4500, // Adjusted price
        type: 'Van',
        seats: '10 Seats',
        imageUrl: 'https://www.thanatwit.com/wp-content/uploads/2022/07/van-5-1.jpg',
        darkImageUrl: 'https://www.thanatwit.com/wp-content/uploads/2022/07/van-5-1.jpg',
        fastBooking: true,
        registrationNumber: 'VAN-1122',
    },
]);
</script>
