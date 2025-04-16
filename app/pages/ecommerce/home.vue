<template>
    <UContainer>
        <section class="bg-white dark:bg-gray-900">
            <div class="max-w-screen-xl px-4 py-8 mx-auto sm:py-12 sm:px-6 lg:px-8">
                <div class="max-w-xl mx-auto text-center">
                    <h2 class="text-3xl font-bold tracking-tight text-gray-900 sm:text-3xl dark:text-white">
                        สินค้าและบริการทั้งหมด
                    </h2>
                </div>

                <div class="grid grid-cols-1 gap-4 mt-8 sm:grid-cols-2 lg:grid-cols-5">
                    <a v-for="product in products"
                       :key="product.title"
                       :href="product.link"
                       class="block transition border border-gray-100 shadow-xl rounded-xl hover:shadow-lg hover:border-gray-200 bg-white dark:bg-white dark:border-gray-200">
                        <img class="h-48 w-full object-cover rounded-t-xl"
                             :src="product.image"
                             :alt="product.name" />
                        <h3 class="text-md font-bold text-gray-900 dark:text-gray-900 text-center">
                            {{ product.title }}
                        </h3>
                        <p class="mt-1 text-sm text-gray-500 dark:text-gray-500">
                            {{ product.description }}
                        </p>
                    </a>
                </div>
            </div>
        </section>
    </UContainer>
</template>

<script setup lang="ts">
import { ref } from 'vue';

// Define product categories


const products = ref([
    {
        id: 1,
        title: 'เทคโนโลยีเพื่อสุขภาพ การก่อสร้าง และวัสดุเทคโนโลยีด้านวิศวกรรม',
        image: 'https://globcommerce.netlify.app/images/b2.jpg',
        link: '/ecommerce/healthTech',
    },
    {
        id: 2,
        title: 'นวัตกรรมสินค้ากรีนโปรดักส์',
        image: '/images/pp2.jpg',
        link: '/ecommerce/greenProducts',
    },
    {
        id: 3,
        title: 'การสื่อสาร การตลาด การท่องเที่ยว และศิลปวัฒนธรรม',
        image: 'https://media.graphassets.com/resize=fit:crop,width:1200,height:630/F33znRaQCmGGjS7jHG52',
        link: '/ecommerce/communication',
    },
    {
        id: 4,
        title: 'ศูนย์การเรียนรู้พัฒนาธุรกิจและเทคโนโลยี',
        image: '/images/pp3.png',
        link: '/ecommerce/businessTech',
    },
    {
        id: 5,
        title: 'นวัตกรรมการเงิน การลงทุนและการจัดการความเสี่ยงธุรกิจ',
        image: 'https://storage.googleapis.com/techsauce-prod/ugc/uploads/2022/4/Fintech_800.jpg',
        link: '/ecommerce/finance',
    }
]);
</script>
