<template>
    <UContainer>
        <section class="bg-white dark:bg-gray-900">
            <div class="max-w-screen-xl px-4 py-8 mx-auto sm:py-12 sm:px-6 lg:px-8">
                <div class="max-w-xl mx-auto text-center">
                    <h2 class="text-3xl font-bold tracking-tight text-gray-900 sm:text-4xl dark:text-white">
                        นวัตกรรมการพัฒนาธุรกิจ ผู้ประกอบการ การจัดการองค์กร
                    </h2>
                    <p class="mt-4 text-gray-500 dark:text-gray-400">
                        วิชาชีพและการสร้างต้นแบบ ณ เลยพีเพิล และเทคโนโลยี เมตาเวิร์ส
                    </p>
                </div>

                <div class="grid grid-cols-1 gap-4 mt-8 sm:grid-cols-2 lg:grid-cols-4">
                    <a v-for="product in products"
                       :key="product.title"
                       href="#"
                       class="block p-8 transition border border-gray-100 shadow-xl rounded-xl hover:shadow-lg hover:border-gray-200 dark:border-gray-800 dark:shadow-gray-800 dark:hover:border-gray-700">
                        <img :src="product.image"
                             :alt="product.title"
                             class="w-full h-48 mb-4 rounded-lg object-cover" />
                        <h3 class="text-lg font-bold text-gray-900 dark:text-white">
                            {{ product.title }}
                        </h3>
                        <p class="mt-1 text-sm text-gray-500 dark:text-gray-400">
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

// Define your reactive variables
const products = ref([
  {
    title: 'บริการ และรับปรึกษาด้านการสื่อสาร',
    description: 'Free Consultation',
    image: 'https://media.graphassets.com/resize=fit:crop,width:1200,height:630/F33znRaQCmGGjS7jHG52',
  },
  {
    title: 'บริการ และรับปรึกษาด้านการสร้าง Branding Brand DNA',
    description: 'Free Consultation',
    image: 'https://duckyplus.co.th/wp-content/uploads/2022/01/service-brand-dna-service-banner-01.png',
  },
  {
    title: 'บริการ รับปรึกษา และสร้าง Innovation Marketing ด้วย Strategic Wisdom',
    description: 'Free Consultation',
    image: '/images/i1.jpg',
  },
  {
    title: 'นวัตกรรมเวลเนส การท่องเที่ยว และศิลปวัฒนธรรม',
    description: 'Free Consultation',
    image: '/images/i2.png',
  },
  {
    title: 'นวัตกรรมตลาดวิชาชีพ',
    description: 'Free Consultation',
    image: '/images/i4.jpg',
  },
  {
    title: 'นวัตกรรมการเรียนรู้จากถิ่นอริยะสงค์',
    description: 'Free Consultation',
    image: '/images/i3.png',
  },
]);

</script>
