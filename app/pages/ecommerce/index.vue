<template>
    <UContainer>
        <section class="bg-gray-50 py-8 antialiased dark:bg-gray-900 md:py-12">
            <div class="mx-auto max-w-screen-xl px-4 2xl:px-0">
                <!-- Heading -->
                <div class="mb-8 text-center">
                    <h2 class="text-3xl font-extrabold text-gray-900 dark:text-white sm:text-4xl">
                        Product Categories
                    </h2>
                    <p class="mt-2 text-lg text-gray-600 dark:text-gray-400">
                        Explore our wide range of product categories.
                    </p>
                </div>
                <!-- Product Categories -->
                <div class="grid gap-6 sm:grid-cols-2 lg:grid-cols-3">
                    <div v-for="category in categories"
                         :key="category.id"
                         class="relative overflow-hidden rounded-lg border border-gray-200 bg-white shadow-md dark:border-gray-700 dark:bg-gray-800">
                        <a :href="category.link"
                           class="block">
                            <img :src="category.imageUrl"
                                 :alt="category.name"
                                 class="h-48 w-full object-cover">
                        </a>
                        <div class="p-4">
                            <h3 class="text-lg font-semibold text-gray-900 dark:text-white">
                                <a :href="category.link"
                                   class="hover:underline">{{ category.name }}</a>
                            </h3>
                            <p class="mt-2 text-sm text-gray-600 dark:text-gray-400">{{ category.description }}</p>
                        </div>
                    </div>
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
        name: 'Electronics',
        description: 'Discover the latest in electronic devices and gadgets.',
        imageUrl: 'https://flowbite.s3.amazonaws.com/blocks/e-commerce/category-electronics.jpg',
        link: '/',
    },
    {
        id: 2,
        name: 'Fashion',
        description: 'Stay trendy with the latest fashion collections.',
        imageUrl: 'https://flowbite.s3.amazonaws.com/blocks/e-commerce/category-fashion.jpg',
        link: '/',
    },
    {
        id: 3,
        name: 'Home & Living',
        description: 'Upgrade your home with our premium furniture and decor.',
        imageUrl: 'https://flowbite.s3.amazonaws.com/blocks/e-commerce/category-home.jpg',
        link: '/ecommerce/home',
    },
    {
        id: 4,
        name: 'Sports & Outdoors',
        description: 'Gear up for your next adventure with our sports equipment.',
        imageUrl: 'https://flowbite.s3.amazonaws.com/blocks/e-commerce/category-sports.jpg',
        link: '/',
    },
    {
        id: 5,
        name: 'Beauty & Health',
        description: 'Explore our beauty and health products for your wellness.',
        imageUrl: 'https://flowbite.s3.amazonaws.com/blocks/e-commerce/category-beauty.jpg',
        link: '/',
    },
    {
        id: 6,
        name: 'Toys & Games',
        description: 'Find the perfect toys and games for kids of all ages.',
        imageUrl: 'https://flowbite.s3.amazonaws.com/blocks/e-commerce/category-toys.jpg',
        link: '/',
    },
]);
</script>
