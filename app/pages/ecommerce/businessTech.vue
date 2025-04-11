<template>
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
        <div class="max-w-screen-xl px-4 py-8 mx-auto sm:py-12 sm:px-6 lg:px-8">
            <div class="mb-4 grid gap-4 sm:grid-cols-2 md:mb-8 lg:grid-cols-3 xl:grid-cols-4">
                <div v-for="product in products2"
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
                           class="text-lg font-semibold leading-tight text-gray-900 hover:underline dark:text-white">
                            {{ product.name }}
                        </a>
                        <div class="mt-2 flex items-center gap-2">
                            <div class="flex items-center">
                                <svg v-for="n in Math.floor(product.rating)"
                                     :key="n"
                                     class="h-4 w-4 text-yellow-400"
                                     aria-hidden="true"
                                     xmlns="http://www.w3.org/2000/svg"
                                     fill="currentColor"
                                     viewBox="0 0 24 24">
                                    <path
                                          d="M13.8 4.2a2 2 0 0 0-3.6 0L8.4 8.4l-4.6.3a2 2 0 0 0-1.1 3.5l3.5 3-1 4.4c-.5 1.7 1.4 3 2.9 2.1l3.9-2.3 3.9 2.3c1.5 1 3.4-.4 3-2.1l-1-4.4 3.4-3a2 2 0 0 0-1.1-3.5l-4.6-.3-1.8-4.2Z" />
                                </svg>
                            </div>
                            <p class="text-sm font-medium text-gray-900 dark:text-white">{{ product.rating }}</p>
                            <p class="text-sm font-medium text-gray-500 dark:text-gray-400">({{ product.reviews }})</p>
                        </div>
                        <div class="mt-4 flex items-center justify-between gap-4">
                            <p class="text-2xl font-extrabold leading-tight text-gray-900 dark:text-white">
                                ฿ {{ product.price.toLocaleString() }}
                            </p>
                            <UButton to="/ecommerce/orderproduct"
                                     class="inline-flex items-center rounded-lg bg-primary-700 px-5 py-2.5 text-sm font-medium text-white hover:bg-primary-800 focus:outline-none focus:ring-4 focus:ring-primary-300 dark:bg-primary-600 dark:hover:bg-primary-700 dark:focus:ring-primary-800">
                                สั่งสินค้า
                            </UButton>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup lang="ts">
const products = [
    {
        title: "การบริหารจัดการธุรกิจ",
        description: "การจัดการองค์กรและธุรกิจอย่างมีประสิทธิภาพ",
        image: "https://1stcraft.com/wp-content/uploads/2020/05/20200523_1SC_ArticleCover.jpg",
    },
    {
        title: "เมตาเวิร์ส (Metaverse)",
        description: "เทคโนโลยีโลกเสมือนจริงเพื่อการพัฒนาธุรกิจ",
        image: "https://www.nstda.or.th/sci2pub/wp-content/uploads/2022/09/Metaverse.jpg",
    },
    {
        title: "บิ๊กดาต้า (Big Data)",
        description: "การให้บริการข้อมูลขนาดใหญ่เพื่อการตัดสินใจ",
        image: "https://digitalmarketingwow.com/wp-content/uploads/2017/06/Big-Data-%E0%B8%84%E0%B8%B7%E0%B8%AD%E0%B8%AD%E0%B8%B0%E0%B9%84%E0%B8%A3-001.jpg",
    },
    {
        title: "การพัฒนาธุรกิจและผู้ประกอบการ",
        description: "การสร้างต้นแบบและพัฒนาผู้ประกอบการ",
        image: "https://storage.googleapis.com/techsauce-prod/ugc/uploads/2023/2/1676376902_1200X800_13_%E0%B9%80%E0%B8%84%E0%B8%A5%E0%B9%87%E0%B8%94%E0%B8%A5%E0%B8%B1%E0%B8%9A%E0%B8%AA%E0%B8%B9%E0%B9%88%E0%B8%81%E0%B8%B2%E0%B8%A3%E0%B9%80%E0%B8%9B%E0%B9%87%E0%B8%99%E0%B8%9C%E0%B8%B9%E0%B9%89%E0%B8%9B%E0%B8%A3%E0%B8%B0%E0%B8%81%E0%B8%AD%E0%B8%9A%E0%B8%81%E0%B8%B2%E0%B8%A3%E0%B8%97%E0%B8%B5%E0%B9%88%E0%B8%9B%E0%B8%A3%E0%B8%B0%E0%B8%AA%E0%B8%9A%E0%B8%84%E0%B8%A7%E0%B8%B2%E0%B8%A1%E0%B8%AA%E0%B8%B3%E0%B9%80%E0%B8%A3%E0%B9%87%E0%B8%88_.jpg",
    },
];

const products2 = ref([
    {
        id: 1,
        name: 'Apple iMac 27”',
        price: 1499,
        discount: 'Up to 15% off',
        rating: 4.9,
        reviews: 1233,
        imageUrl: 'https://flowbite.s3.amazonaws.com/blocks/e-commerce/imac-front.svg',
        darkImageUrl: 'https://flowbite.s3.amazonaws.com/blocks/e-commerce/imac-front-dark.svg',
        bestSeller: true,
        bestPrice: true,
    },
    {
        id: 2,
        name: 'iPad Pro 13-Inch (M4): XDR Display, 512GB',
        price: 799,
        discount: 'Up to 35% off',
        rating: 4.9,
        reviews: 879,
        imageUrl: 'https://flowbite.s3.amazonaws.com/blocks/e-commerce/ipad-light.svg',
        darkImageUrl: 'https://flowbite.s3.amazonaws.com/blocks/e-commerce/ipad-dark.svg',
        bestSeller: true,
        bestPrice: true,
    },
    {
        id: 3,
        name: 'PlayStation®5 Console – 1TB, PRO Controller',
        price: 499,
        discount: 'Up to 10% off',
        rating: 4.8,
        reviews: 2957,
        imageUrl: 'https://flowbite.s3.amazonaws.com/blocks/e-commerce/ps5-light.svg',
        darkImageUrl: 'https://flowbite.s3.amazonaws.com/blocks/e-commerce/ps5-dark.svg',
        fastDelivery: true,
        bestPrice: true,
    },
    {
        id: 4,
        name: 'Microsoft Xbox Series X 1TB Gaming Console',
        price: 499,
        discount: 'Up to 10% off',
        rating: 4.8,
        reviews: 4263,
        imageUrl: 'https://flowbite.s3.amazonaws.com/blocks/e-commerce/xbox-light.svg',
        darkImageUrl: 'https://flowbite.s3.amazonaws.com/blocks/e-commerce/xbox-dark.svg',
        bestSeller: true,
        bestPrice: true,
    },
    {
        id: 5,
        name: 'Apple MacBook PRO Laptop with M2 chip',
        price: 2599,
        discount: 'Up to 5% off',
        rating: 4.9,
        reviews: 1076,
        imageUrl: 'https://flowbite.s3.amazonaws.com/blocks/e-commerce/macbook-pro-light.svg',
        darkImageUrl: 'https://flowbite.s3.amazonaws.com/blocks/e-commerce/macbook-pro-dark.svg',
        fastDelivery: true,
        bestPrice: true,
    },
    {
        id: 6,
        name: 'Apple Watch SE [GPS 40mm], Smartwatch',
        price: 699,
        discount: 'Up to 20% off',
        rating: 4.7,
        reviews: 387,
        imageUrl: 'https://flowbite.s3.amazonaws.com/blocks/e-commerce/apple-watch-light.svg',
        darkImageUrl: 'https://flowbite.s3.amazonaws.com/blocks/e-commerce/apple-watch-dark.svg',
        fastDelivery: true,
        bestPrice: true,
    },
    {
        id: 7,
        name: 'Microsoft Surface Pro, Copilot+ PC, 13 Inch',
        price: 899,
        discount: 'Up to 35% off',
        rating: 4.9,
        reviews: 4775,
        imageUrl: 'https://flowbite.s3.amazonaws.com/blocks/e-commerce/ipad-keyboard.svg',
        darkImageUrl: 'https://flowbite.s3.amazonaws.com/blocks/e-commerce/ipad-keyboard-dark.svg',
        fastDelivery: true,
        bestPrice: true,
    },
]);
</script>
