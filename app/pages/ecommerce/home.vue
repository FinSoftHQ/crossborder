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
        image: 'http://localhost:3000/images/b1.jpg',
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
        image: 'https://1stcraft.com/wp-content/uploads/2020/05/20200523_1SC_ArticleCover.jpg',
        link: '/ecommerce/communication',
    },
    {
        id: 4,
        title: 'ศูนย์การเรียนรู้พัฒนาธุรกิจและเทคโนโลยี',
        image: 'https://storage.googleapis.com/techsauce-prod/ugc/uploads/2023/2/1676376902_1200X800_13_%E0%B9%80%E0%B8%84%E0%B8%A5%E0%B9%87%E0%B8%94%E0%B8%A5%E0%B8%B1%E0%B8%9A%E0%B8%AA%E0%B8%B9%E0%B9%88%E0%B8%81%E0%B8%B2%E0%B8%A3%E0%B9%80%E0%B8%9B%E0%B9%87%E0%B8%99%E0%B8%9C%E0%B8%B9%E0%B9%89%E0%B8%9B%E0%B8%A3%E0%B8%B0%E0%B8%81%E0%B8%AD%E0%B8%9A%E0%B8%81%E0%B8%B2%E0%B8%A3%E0%B8%97%E0%B8%B5%E0%B9%88%E0%B8%9B%E0%B8%A3%E0%B8%B0%E0%B8%AA%E0%B8%9A%E0%B8%84%E0%B8%A7%E0%B8%B2%E0%B8%A1%E0%B8%AA%E0%B8%B3%E0%B9%80%E0%B8%A3%E0%B9%87%E0%B8%88_.jpg',
        link: '/ecommerce/businessTech',
    },
    {
        id: 5,
        title: 'นวัตกรรมการเงิน การลงทุนและการจัดการความเสี่ยงธุรกิจ',
        image: 'https://www.exim.go.th/eximinter/e-news/20341/image/finance/chart-1.jpg',
        link: '/ecommerce/finance',
    }
]);
</script>
