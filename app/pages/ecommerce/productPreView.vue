<template>
    <UContainer>
        <section class="bg-gray-50 py-8 antialiased dark:bg-gray-900 md:py-12">
            <div class="mx-auto max-w-screen-xl px-4 2xl:px-0">
                <!-- Heading & Filters -->
                <div class="items-end justify-between space-y-4 sm:flex sm:space-y-0 md:mb-8">
                    <div class="mb-2 text-center">
                        <p class="mt-2 text-lg text-gray-600 dark:text-gray-400">
                        <h2 class="text-3xl font-extrabold text-gray-900 dark:text-white sm:text-4xl">
                            สินค้าที่ลงทะเบียน
                        </h2>
                    </p>
                </div>
                </div>
                <div class="mb-4 grid gap-4 sm:grid-cols-2 md:mb-8 lg:grid-cols-3 xl:grid-cols-4">

                    <div v-for="product in products"
                         :key="product.id"
                         class="rounded-lg border border-gray-200 bg-white p-6 shadow-sm dark:border-gray-700 dark:bg-gray-800">
                        <div class="h-56 w-full">
                            <a href="#">
                                <img :src="product.imageUrl"
                                     class="mx-auto h-full dark:hidden"
                                     :alt="product.name" />
                                <img :src="product.darkImageUrl"
                                     class="mx-auto hidden h-full dark:block"
                                     :alt="product.name" />
                            </a>
                        </div>
                        <div class="pt-6">                           
                            <a href="#"
                               class="text-lg font-semibold leading-tight text-gray-900 hover:underline dark:text-white">{{
                                product.name }}</a>
                            <div class="mt-2 flex items-center gap-2">
                                <div class="flex items-center">                                    
                                </div>
                                <p class="text-sm font-medium text-gray-900 dark:text-white">{{ product.rating }}</p>
                                <p class="text-sm font-medium text-gray-500 dark:text-gray-400">({{ product.reviews }})
                                </p>
                            </div>                          
                           
                        </div>
                    </div>

                </div>
                <div class="w-full text-center">
                    <button type="button"
                            class="rounded-lg border border-gray-200 bg-white px-5 py-2.5 text-sm font-medium text-gray-900 hover:bg-gray-100 hover:text-primary-700 focus:z-10 focus:outline-none focus:ring-4 focus:ring-gray-100 dark:border-gray-600 dark:bg-gray-800 dark:text-gray-400 dark:hover:bg-gray-700 dark:hover:text-white dark:focus:ring-gray-700">Show
                        more</button>
                </div>
            </div>
            <!-- Filter modal -->

        </section>
    </UContainer>
</template>
<script setup lang="ts">
import { ref } from 'vue';

// Define your reactive variables
const products = ref([
    {
        id: 1,
        name: 'Apple',
        price: 1.5,
        rating: 4.8,
        reviews: 120,
        imageUrl: 'https://example.com/images/apple-light.svg',
        darkImageUrl: 'https://example.com/images/apple-dark.svg',
        bestSeller: true,
        bestPrice: true,
    },
    {
        id: 2,
        name: 'Banana',
        price: 0.5,
        rating: 4.7,
        reviews: 98,
        imageUrl: 'https://example.com/images/banana-light.svg',
        darkImageUrl: 'https://example.com/images/banana-dark.svg',
        bestSeller: true,
        fastDelivery: true,
    },
    {
        id: 3,
        name: 'Cherry',
        price: 3.0,
        discount: 'Up to 20% off',
        rating: 4.9,
        reviews: 150,
        imageUrl: 'https://example.com/images/cherry-light.svg',
        darkImageUrl: 'https://example.com/images/cherry-dark.svg',
        bestPrice: true,
    },
    {
        id: 4,
        name: 'Grapes',
        price: 2.5,
        discount: 'Up to 5% off',
        rating: 4.6,
        reviews: 75,
        imageUrl: 'https://example.com/images/grapes-light.svg',
        darkImageUrl: 'https://example.com/images/grapes-dark.svg',
        fastDelivery: true,
    },
    {
        id: 5,
        name: 'Orange',
        price: 1.2,
        rating: 4.7,
        reviews: 110,
        imageUrl: 'https://example.com/images/orange-light.svg',
        darkImageUrl: 'https://example.com/images/orange-dark.svg',
        bestSeller: true,
    },
    {
        id: 6,
        name: 'Pineapple',
        price: 3.5,
        rating: 4.8,
        reviews: 90,
        imageUrl: 'https://example.com/images/pineapple-light.svg',
        darkImageUrl: 'https://example.com/images/pineapple-dark.svg',
        bestPrice: true,
    },
    {
        id: 7,
        name: 'Strawberry',
        price: 4.0,
        rating: 4.9,
        reviews: 200,
        imageUrl: 'https://example.com/images/strawberry-light.svg',
        darkImageUrl: 'https://example.com/images/strawberry-dark.svg',
        fastDelivery: true,
    },
]);
</script>