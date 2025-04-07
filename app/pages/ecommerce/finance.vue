<template>
    <section class="bg-white dark:bg-gray-900">
        <div class="max-w-screen-xl px-4 py-8 mx-auto sm:py-12 sm:px-6 lg:px-8">
            <div class="max-w-xl mx-auto text-center">
            <h2 class="text-3xl font-bold tracking-tight text-gray-900 sm:text-4xl dark:text-white">
                นวัตกรรมการเงิน การลงทุนและการจัดการความเสี่ยงธุรกิจ
            </h2>          
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
</template>

<script setup lang="ts">
const products = [
    {
        title: "นวัตกรรมการเงิน การบัญชี ภาษี ไฟแนนซ์",
        description: "การพัฒนาระบบการเงินและการจัดการบัญชีที่ทันสมัย",
        image: "https://via.placeholder.com/150",
    },
    {
        title: "นวัตกรรมประกันภัย และบริหารความเสี่ยง",
        description: "การจัดการความเสี่ยงและการประกันภัยที่มีประสิทธิภาพ",
        image: "https://via.placeholder.com/150",
    },
    {
        title: "นวัตกรรมกางกฏหมาย และคดีความ",
        description: "การใช้เทคโนโลยีเพื่อการจัดการกฎหมายและคดีความ",
        image: "https://via.placeholder.com/150",
    },
    {
        title: "ณ เลย ฟินเทค",
        description: "การพัฒนาเทคโนโลยีทางการเงินเพื่อธุรกิจ",
        image: "https://via.placeholder.com/150",
    },
    {
        title: "การจัดการสินทรัพย์/หนี้สิน",
        description: "การบริหารสินทรัพย์และหนี้สินอย่างมีประสิทธิภาพ",
        image: "https://via.placeholder.com/150",
    },
    {
        title: "การจัดการนิติบุคคล",
        description: "การบริหารจัดการนิติบุคคลและองค์กร",
        image: "https://via.placeholder.com/150",
    },
    {
        title: "บริการซื้อ-เช่าสินทรัพย์ แก้ปรับโครงสร้างและซื้อ-ขายธุรกิจ",
        description: "บริการที่ครอบคลุมการจัดการสินทรัพย์และธุรกิจ",
        image: "https://via.placeholder.com/150",
    },
    {
        title: "การจัดการธุรกิจที่ยั่งยืน",
        description: "การพัฒนาธุรกิจที่เป็นมิตรต่อสิ่งแวดล้อมและยั่งยืน",
        image: "https://via.placeholder.com/150",
    },
    {
        title: "กองทุน สหกรณ์ มูลนิธิ",
        description: "การบริหารจัดการกองทุน สหกรณ์ และมูลนิธิ",
        image: "https://via.placeholder.com/150",
    },
    {
        title: "สถาบันการเงิน",
        description: "การพัฒนาสถาบันการเงินเพื่อการเติบโตทางเศรษฐกิจ",
        image: "https://via.placeholder.com/150",
    },
];
</script>