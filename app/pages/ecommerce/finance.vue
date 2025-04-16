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
        image: "https://www.exim.go.th/eximinter/e-news/20341/image/finance/chart-1.jpg",
    },
    {
        title: "นวัตกรรมประกันภัย และบริหารความเสี่ยง",
        description: "การจัดการความเสี่ยงและการประกันภัยที่มีประสิทธิภาพ",
        image: "https://storage.googleapis.com/techsauce-prod/ugc/uploads/2022/4/Fintech_800.jpg",
    },
    {
        title: "นวัตกรรมกางกฏหมาย และคดีความ",
        description: "การใช้เทคโนโลยีเพื่อการจัดการกฎหมายและคดีความ",
        image: "https://tiins.com/wp-content/uploads/2019/10/checklist-management-1-1030x412.png",
    },
    {
        title: "ณ เลย ฟินเทค",
        description: "การพัฒนาเทคโนโลยีทางการเงินเพื่อธุรกิจ",
        image: "https://tiins.com/wp-content/uploads/2019/10/objectives-of-performance-management.png",
    },
    {
        title: "การจัดการสินทรัพย์/หนี้สิน",
        description: "การบริหารสินทรัพย์และหนี้สินอย่างมีประสิทธิภาพ",
        image: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcT3l7Vd2s-DQQ34x-gybwq8NYcFIXsKCxA4wHtSQXsqsc86xrTCqTkWo4vdDoqmZGPvXFs&usqp=CAU",
    },
    {
        title: "การจัดการนิติบุคคล",
        description: "การบริหารจัดการนิติบุคคลและองค์กร",
        image: "https://www.smarttoinvest.com/PublishingImages/Pages/InvestmentProduct/KnowInvestment/Insurance/%E0%B8%9A%E0%B8%A3%E0%B8%B4%E0%B8%AB%E0%B8%B2%E0%B8%A3.png",
    },
    {
        title: "บริการซื้อ-เช่าสินทรัพย์ แก้ปรับโครงสร้างและซื้อ-ขายธุรกิจ",
        description: "บริการที่ครอบคลุมการจัดการสินทรัพย์และธุรกิจ",
        image: "https://sim239.com/berded/289_1.png",
    },
    {
        title: "การจัดการธุรกิจที่ยั่งยืน",
        description: "การพัฒนาธุรกิจที่เป็นมิตรต่อสิ่งแวดล้อมและยั่งยืน",
        image: "https://thaipublica.org/wp-content/uploads/2020/04/%E0%B8%87%E0%B8%9A%E0%B8%81%E0%B8%B2%E0%B8%A3%E0%B9%80%E0%B8%87%E0%B8%B4%E0%B8%99%E0%B8%81%E0%B8%B1%E0%B8%9A%E0%B9%81%E0%B8%9A%E0%B8%87%E0%B8%81%E0%B9%8C%E0%B8%8A%E0%B8%B2%E0%B8%95%E0%B8%B4-02_thaipublica-scaled-e1587552294231.jpg",
    },
    {
        title: "กองทุน สหกรณ์ มูลนิธิ",
        description: "การบริหารจัดการกองทุน สหกรณ์ และมูลนิธิ",
        image: "https://promotions.co.th/wp-content/uploads/2023/08/what-is-financial-liquidity.jpg",
    },
    {
        title: "สถาบันการเงิน",
        description: "การพัฒนาสถาบันการเงินเพื่อการเติบโตทางเศรษฐกิจ",
        image: "https://www.myaccount-cloud.com/upload/8567/ssyf8GJKV2.jpg",
    },
];
</script>
