<template>
    <UContainer>
        <section class="bg-gray-50 py-8 antialiased dark:bg-gray-900 md:py-12">
            <div>
                <UAlert
                    title="คำสั่งซื้อ"
                    description="สินค้าของคุณได้รับคำสั่งซื้อเรียบร้อยแล้ว กรุณาเตรียมจัดส่งสินค้า"
                    :actions="[
                        { label: 'ดูรายละเอียด', to: '/ecommerce/orderdetail' },
                        { label: 'ปิด', color: 'neutral', variant: 'subtle' }
                    ]"
                />
            </div>
            <div class="mx-auto max-w-screen-xl px-4 2xl:px-0">
                <!-- Heading & Filters -->
                <div class="mb-4 items-end justify-between space-y-4 sm:flex sm:space-y-0 md:mb-8">
                    <div>
                        <nav class="flex"
                             aria-label="Breadcrumb">
                        </nav>
                        <h2 class="mt-3 text-xl font-semibold text-gray-900 dark:text-white sm:text-2xl">สินค้าลงขาย
                        </h2>

                    </div>
                </div>
                <div class="mb-4 grid gap-4 sm:grid-cols-2 md:mb-8 lg:grid-cols-3 xl:grid-cols-4">

                    <div v-for="product in products"
                         :key="product.id"
                         class="rounded-lg border border-gray-200 bg-white p-6 shadow-sm dark:border-gray-700 dark:bg-gray-800">
                        <div class="h-56 w-full">
                            <a href="#" @click.prevent="handleQRCodeClick(product)">
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
                                <p class="text-sm font-medium text-gray-900 dark:text-white">{{ product.weight }}</p>
                                <p class="text-sm font-medium text-gray-500 dark:text-gray-400">({{ product.reviews }})
                                </p>
                            </div>
                        </div>
                        <div class="mt-4 flex items-center justify-between gap-4">
                            <p class="text-2xl font-extrabold leading-tight text-gray-900 dark:text-white">฿ {{
                                product.price }}</p>
                            <UButton
                                     class="inline-flex items-center rounded-lg bg-primary-700 px-5 py-2.5 text-sm font-medium text-white hover:bg-primary-800 focus:outline-none focus:ring-4 focus:ring-primary-300 dark:bg-primary-600 dark:hover:bg-primary-700 dark:focus:ring-primary-800">
                                <svg class="-ms-2 me-2 h-5 w-5"
                                     aria-hidden="true"
                                     xmlns="http://www.w3.org/2000/svg"
                                     width="24"
                                     height="24"
                                     fill="none"
                                     viewBox="0 0 24 24">
                                    <path stroke="currentColor"
                                          stroke-linecap="round"
                                          stroke-linejoin="round"
                                          stroke-width="2"
                                          d="M16.862 3.487a2.06 2.06 0 0 1 2.914 2.914L7.425 18.752a4.5 4.5 0 0 1-1.697 1.1l-3.18 1.06 1.06-3.18a4.5 4.5 0 0 1 1.1-1.697L16.862 3.487Z" />
                                </svg>
                                ปรับราคา
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
            <!-- Filter modal -->

        </section>
    </UContainer>
</template>
<script setup lang="ts">
import { ref, inject } from 'vue';

const showAlert = ref(false);

// Inject the shared state
const triggerAlert = inject('triggerAlert');

// Watch for changes in the shared state
if (triggerAlert) {
    triggerAlert.value = () => {
        showAlert.value = true;
    };
}

// Define your reactive variables
const products = ref([
    {
        id: 1,
        name: 'Apple',
        price: 120, // Adjusted price
        rating: 4.8,
        reviews: 'สด / แห้ง',
        weight: '100 kg',
        imageUrl: 'https://home.maefahluang.org/images/editor/apple.jpg',
        darkImageUrl: 'https://example.com/images/apple-dark.svg',
        bestSeller: true,
        bestPrice: true,
    },
    {
        id: 2,
        name: 'Banana',
        price: 50, // Adjusted price
        reviews: 'สด / แห้ง',
        weight: '100 kg',
        imageUrl: 'https://fit-d.com/uploads/food/5f6c8c69a8f190b979f93f02475aac80.jpg',
        darkImageUrl: 'https://example.com/images/banana-dark.svg',
        bestSeller: true,
        fastDelivery: true,
    },
    {
        id: 3,
        name: 'Cherry',
        price: 150, // Adjusted price
        discount: 'Up to 20% off',
        rating: 4.9,
        reviews: 'สด / แห้ง',
        weight: '120 kg',
        imageUrl: 'https://upload.wikimedia.org/wikipedia/commons/f/f6/Cherry_season_%2848216568227%29.jpg',
        darkImageUrl: 'https://example.com/images/cherry-dark.svg',
        bestPrice: true,
    },
    {
        id: 4,
        name: 'Grapes',
        price: 90, // Adjusted price
        discount: 'Up to 5% off',
        rating: 4.6,
        reviews: 'สด / แห้ง',
        weight: '30 kg',
        imageUrl: 'https://i0.wp.com/www.freshfoodsbkk.com/wp-content/uploads/2017/08/grapes-red.jpg?fit=500%2C500&ssl=1',
        darkImageUrl: 'https://example.com/images/grapes-dark.svg',
        fastDelivery: true,
    },
    {
        id: 5,
        name: 'Orange',
        price: 100, // Adjusted price
        rating: 4.7,
        reviews: 'สด / แห้ง',
        weight: '400 kg',
        imageUrl: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRZbB_doR9LVg_xVbDXOOZc3TNbgNCEIzLLKw&s',
        darkImageUrl: 'https://example.com/images/orange-dark.svg',
        bestSeller: true,
    },
    {
        id: 6,
        name: 'Pineapple',
        price: 80, // Adjusted price
        rating: 4.8,
        reviews: 'สด / แห้ง',
        weight: '100 kg',
        imageUrl: 'data:image/jpeg;base64,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',
        darkImageUrl: 'https://example.com/images/pineapple-dark.svg',
        bestPrice: true,
    },
    {
        id: 7,
        name: 'Strawberry',
        price: 180, // Adjusted price
        rating: 4.9,
    reviews: 200,
    weight: '100 kg',
    imageUrl: 'data:image/jpeg;base64,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hdOHpAEAQBAeXoCs2lSa9pa8AtOoKhJJqzLKc5Rd4ux8423sPdklhkRA6jsRz9VknStwe7p9ap4nhlO5rgRJ0sTp8/VQSdsmlyg8o1VWkfinuVPbixVuXJW4moNA6f1/+Lt7EHNcl/4YrkU3sGoOYA2kKucE5b0ToTjuUX+XJeL2s9oBFNxaYzXkgc8osPdUucXiPJ6dLSwk2tyv9/UjYrbW9JLaRptHlDrmAPxHSSVGLaWS2jovDXVK77/sV9XF5xALgA0BxJiX6mI5DRV05TTe5mmNNQebe70IJqx8RcdOYjqXEz7KbcrljnZ4tY0knPZxI0udB/CltS4ISrJR4NVaoQYz5g2wgyL9EjDvaxV4uL2tf5m0sc8NAdmMHhE8I/ZdTSbwZ1WSk01b18zZhXZy1kGAZyibn09112WSUntTlfL7m8OG8PDAm7RaItHpPNcSG/oSuXmDqB7gRAd5WhoFh9XKUYXdjFV6I+nJ9E8MbO+y0YN3uOZ/bo35D9ZXo047UfN6qv4079i6Y9TMzN7V0iekAQBAEBghARsRQlcZ1MpcfsfOotXLVOxTV/CDHaqHhoujqJIjnwTS+ElPDR3+JkbKfg+mNGJ4aOPUMlUvDbW3DYXdiI+MyPjvDTyPu3R+V1x3I6LNLSR3bo8npab2ntf9RX9Vz8TncbsetSYBVYA0WzgSfV0alZv4Z025Hr0tbQqTvBu/k/sc9Udkhm8GUmTqATyLgRaOyjszdo9CU4ye+2UQftJpuOU+rm3t2Utiayiqo1OOUaq2pyOLmjmAR7ypJOxCM211YM4mCwODQBprc9zdEimLtPLMb8Na3ISHfivYj6Ltmcy293BsZXLTZwM3cRaO113acck1lEujVk5ATfzQJn5ld23KZVlHLOx8N4ZtMh0S4eWdGzrHfur6dNRyeTq9TKrjsdrgnuctCPNdlwW9FikQbJAC6RMoAgCAIAgCA8loQGN2EO3MbodFywuN0F2wuYNMJY4eH01yxIi1qXZcaudXmc7tTYVKr5qDHf8Ar/CrcF5GqnqqkOJM5bH+CaR8tIt/6ucPqo+GjZH2jVXf6FTX8D1DZheBzE6+tlHwy3+Yt/qsR2eAcUdCfmE2M7/Mifh/+Na7rvqx1XVSZVL2j6F1gv8AjZrfM9xUvCKJ6+ci9wPgylT0b7qSgkZpaiT7l5hdjsZo1SSKXNssqVADkpWIXNwC6cMoAgCAIAgCAIAgCAIAgCAxCA85AgPO5HRcsduY+zt6JYXH2dvRLC56FEdEFzO7CHDOQLoMwgMoAgCAIAgCAIAgCAIAgCAIAgCAIAgCAIAgCAIAgCAIAgCAIAgCAIAgCAIAgCAIAgCAIAgCAIAgCAIAgCAIAgCAIAgCAIAgCAIAgCAIAgCAIAgCAIAgCAIAgCAIAgCAIAgCAIAgCAIAgCAIAgCAIAgCAIAgCAIAgCAIAgCAIAgCAIAgCAIAgCAIAgCAIAgCAIAgCAIAgCAIAgCAIAgCAIAgCAIAgCAIAgCAIAgCAIAgCAIAgCAIAgCAIAgCAIAgCAIAgCAIAgCAIAgCAIAgCAIAgCAIAgCAIAgCA//Z',
    darkImageUrl: 'https://example.com/images/strawberry-dark.svg',
    fastDelivery: true,
  },
]);

// Method to handle QR code click
function handleQRCodeClick(product) {
    console.log(`QR code clicked for product: ${product.name}`);
    showAlert.value = true; // Trigger the alert
}
</script>
