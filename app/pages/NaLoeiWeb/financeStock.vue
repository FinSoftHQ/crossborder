<template>
    <section class="bg-white py-8 antialiased dark:bg-gray-900 md:py-16">
        <div class="mx-auto max-w-screen-xl px-4 2xl:px-0">
            <div class="mx-auto max-w-5xl">
                <div class="gap-4 lg:flex lg:items-center lg:justify-between mb-4">
                    <h2 class="text-xl font-semibold text-gray-900 dark:text-white sm:text-2xl">การเงิน</h2>
                    <div class="flex items-center space-x-4">
                        <label for="reportFilter"
                               class="text-sm font-medium text-gray-700 dark:text-gray-300">เลือกช่วงเวลา:</label>
                        <select id="reportFilter"
                                v-model="selectedFilter"
                                class="block w-40 px-3 py-2 bg-white border border-gray-300 rounded-md shadow-sm focus:outline-none focus:ring-blue-500 focus:border-blue-500 sm:text-sm">
                            <option value="daily">รายวัน</option>
                            <option value="weekly">ราย 7 วัน</option>
                            <option value="monthly">รายเดือน</option>
                        </select>
                    </div>
                </div>
                <!-- Card Section -->
                <div class="grid grid-cols-1 gap-6 sm:grid-cols-3 mb-8">
                    <div class="p-6 bg-white rounded-lg shadow dark:bg-white flex items-center space-x-4">
                        <div class="flex items-center justify-center w-12 h-12 bg-green-100 rounded-full">
                            <svg class="w-6 h-6 text-green-500"
                                 xmlns="http://www.w3.org/2000/svg"
                                 fill="none"
                                 viewBox="0 0 24 24"
                                 stroke="currentColor">
                                <path stroke-linecap="round"
                                      stroke-linejoin="round"
                                      stroke-width="2"
                                      d="M12 8c-1.657 0-3 1.343-3 3s1.343 3 3 3 3-1.343 3-3-1.343-3-3-3zm0 0c-4.418 0-8 3.582-8 8h16c0-4.418-3.582-8-8-8z" />
                            </svg>
                        </div>
                        <div>
                            <h3 class="text-lg font-semibold text-gray-900">รายได้รวมทั้งหมด</h3>
                            <p class="mt-1 text-2xl font-bold text-gray-900">{{ totalRevenue.toLocaleString() }}</p>
                        </div>
                    </div>
                    <div class="p-6 bg-white rounded-lg shadow dark:bg-white flex items-center space-x-4">
                        <div class="flex items-center justify-center w-12 h-12 bg-blue-100 rounded-full">
                            <svg class="w-6 h-6 text-blue-500"
                                 xmlns="http://www.w3.org/2000/svg"
                                 fill="none"
                                 viewBox="0 0 24 24"
                                 stroke="currentColor">
                                <path stroke-linecap="round"
                                      stroke-linejoin="round"
                                      stroke-width="2"
                                      d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z" />
                            </svg>
                        </div>
                        <div>
                            <h3 class="text-lg font-semibold text-gray-900">รายได้ส่วนต่างทั้งหมด</h3>
                            <p class="mt-1 text-2xl font-bold text-gray-900">{{ totalOwnerRevenue.toLocaleString() }}
                            </p>
                        </div>
                    </div>
                    <div class="p-6 bg-white rounded-lg shadow dark:bg-white flex items-center space-x-4">
                        <div class="flex items-center justify-center w-12 h-12 bg-yellow-100 rounded-full">
                            <svg class="w-6 h-6 text-yellow-500"
                                 xmlns="http://www.w3.org/2000/svg"
                                 fill="none"
                                 viewBox="0 0 24 24"
                                 stroke="currentColor">
                                <path stroke-linecap="round"
                                      stroke-linejoin="round"
                                      stroke-width="2"
                                      d="M3 10h11M9 21V3m0 0L3 10m6-7l6 7" />
                            </svg>
                        </div>
                        <div>
                            <h3 class="text-lg font-semibold text-gray-900">รายได้แบ่งให้ร้านค้าทั้งหมด</h3>
                            <p class="mt-1 text-2xl font-bold text-gray-900">{{ totalStoreShare.toLocaleString() }}</p>
                        </div>
                    </div>
                </div>
                <div class="grid grid-cols-1 gap-4 sm:grid-cols-2 lg:grid-cols-5 mb-8">
                    <div v-for="(total, category) in categoryTotals"
                         :key="category"
                         class="p-4 bg-white rounded-lg shadow dark:bg-white">
                        <h3 class="text-lg font-semibold text-gray-900">{{ category }}</h3>
                        <p class="mt-2 text-md text-gray-600">รายได้ทั้งหมด: <span class="font-medium text-gray-900">{{
                            total.revenue.toLocaleString() }}</span></p>
                        <!-- <p class="mt-2 text-sm text-gray-600">แบ่งให้ร้านค้า: <span class="font-medium text-gray-900">{{
                            total.storeShare.toLocaleString() }}</span></p> -->
                    </div>
                </div>
                <div class="mt-6 flow-root sm:mt-8">
                    <div class="overflow-x-auto relative shadow-md sm:rounded-lg">
                        <table class="w-full text-sm text-left text-gray-500 dark:text-gray-400">
                            <thead
                                   class="text-xs text-gray-700 uppercase bg-gray-50 dark:bg-gray-700 dark:text-gray-400">
                                <tr>
                                    <th scope="col"
                                        class="px-6 py-3">ชื่อสินค้า</th>
                                    <th scope="col"
                                        class="px-6 py-3">ประเภท</th>
                                    <th scope="col"
                                        class="px-6 py-3">รายได้รวม</th>
                                    <th scope="col"
                                        class="px-6 py-3">ส่วนต่างที่ได้</th>
                                    <th scope="col"
                                        class="px-6 py-3">แบ่งให้ร้านค้า</th>
                                </tr>
                            </thead>
                            <tbody>
                                <tr v-for="product in products"
                                    :key="product.id"
                                    class="bg-white border-b dark:bg-gray-800 dark:border-gray-700">
                                    <td class="px-6 py-4 font-medium text-gray-900 dark:text-white">{{ product.name }}
                                    </td>
                                    <td class="px-6 py-4">{{ product.category }}</td>
                                    <td class="px-6 py-4">{{ product.revenue.toLocaleString() }}</td>
                                    <td class="px-6 py-4">{{ product.ownerMargin.toLocaleString() }}</td>
                                    <td class="px-6 py-4">{{ product.storeShare.toLocaleString() }}</td>
                                </tr>
                            </tbody>
                        </table>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup lang="ts">
import { ref, computed } from 'vue';

interface Product {
    id: number;
    name: string;
    category: string;
    quantity: number;
    image: string;
    stores: number;
    revenue: number; // รายได้รวม
    storeShare: number; // รายได้แบ่งให้ร้านค้า
    ownerMargin: number; // ส่วนต่างที่ได้
}

const selectedFilter = ref('daily'); // Default filter

const products = ref<Product[]>([
    // สด / แห้ง
    { id: 1, name: "Apple", category: "สด / แห้ง", quantity: 50, image: "https://home.maefahluang.org/images/editor/apple.jpg", stores: 10, revenue: 5000, storeShare: 2500 },
    { id: 2, name: "Banana", category: "สด / แห้ง", quantity: 30, image: "https://fit-d.com/uploads/food/5f6c8c69a8f190b979f93f02475aac80.jpg", stores: 8, revenue: 3000, storeShare: 1500 },
    { id: 3, name: "Cherry", category: "สด / แห้ง", quantity: 100, image: "https://upload.wikimedia.org/wikipedia/commons/f/f6/Cherry_season_%2848216568227%29.jpg", stores: 12, revenue: 10000, storeShare: 5000 },

    // ผง
    { id: 4, name: "Matcha Powder", category: "ผง", quantity: 20, image: "https://i.etsystatic.com/26840043/r/il/4509f0/5299934659/il_fullxfull.5299934659_dhb7.jpg", stores: 5, revenue: 2000, storeShare: 1000 },
    { id: 5, name: "Cocoa Powder", category: "ผง", quantity: 15, image: "https://cdn.shopify.com/s/files/1/0229/2203/files/cocoa_powder.png?v=1692687871", stores: 7, revenue: 1500, storeShare: 750 },
    { id: 6, name: "Turmeric Powder", category: "ผง", quantity: 25, image: "https://domf5oio6qrcr.cloudfront.net/medialibrary/15065/conversions/fa246ce0-054b-4892-bf30-5eb43cd938aa-thumb.jpg", stores: 6, revenue: 2500, storeShare: 1250 },

    // สารสกัด
    { id: 7, name: "Green Tea Extract", category: "สารสกัด", quantity: 10, image: "https://www.disthai.com/images/content/original-1680925806479.jpg", stores: 4, revenue: 1000, storeShare: 500 },
    { id: 8, name: "Ginseng Extract", category: "สารสกัด", quantity: 12, image: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTdzmZQZvYGFfAcWkJAXesah4Bebn9gs32aMg&s", stores: 3, revenue: 1200, storeShare: 600 },
    { id: 9, name: "Aloe Vera Extract", category: "สารสกัด", quantity: 18, image: "https://inwfile.com/s-b/ldg7ue.jpg", stores: 5, revenue: 1800, storeShare: 900 },

    // ผลิตภัณฑ์ green product (ของกิน ของใช้)
    { id: 10, name: "Eco-Friendly Soap", category: "ผลิตภัณฑ์ (ของกิน ของใช้)", quantity: 40, image: "https://kj1bcdn.b-cdn.net/media/55090/bar.jpeg", stores: 9, revenue: 4000, storeShare: 2000 },
    { id: 11, name: "Reusable Bag", category: "ผลิตภัณฑ์ (ของกิน ของใช้)", quantity: 60, image: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQlDuSgdzmKiuSiGAiK0DHMEmLXytljB5iwzg&s", stores: 15, revenue: 6000, storeShare: 3000 },
    { id: 12, name: "Bamboo Toothbrush", category: "ผลิตภัณฑ์ (ของกิน ของใช้)", quantity: 35, image: "https://zerowastecartel.com/cdn/shop/products/10-pack-of-bamboo-toothbrushes-671048_1445x.jpg?v=1692183433", stores: 10, revenue: 3500, storeShare: 1750 },

    // อาหารเสริม
    { id: 13, name: "Vitamin C", category: "อาหารเสริม", quantity: 50, image: "https://res.cloudinary.com/dk0z4ums3/image/upload/v1708488896/attached_image_th/%E0%B8%A7%E0%B8%B4%E0%B8%95%E0%B8%B2%E0%B8%A1%E0%B8%B4%E0%B8%99%E0%B8%8B%E0%B8%B5.jpg", stores: 20, revenue: 5000, storeShare: 2500 },
]);

// Update store share and calculate owner margin
products.value.forEach(product => {
    product.storeShare = product.revenue * 0.85;
    product.ownerMargin = product.revenue - product.storeShare;
});

// Filtered products based on selected filter
const filteredProducts = computed(() => {
    // Logic to filter products based on `selectedFilter`
    // For now, it returns all products as a placeholder
    return products.value; // Replace with actual filtering logic
});

// Compute total revenue and store share by category
const categoryTotals = computed(() => {
    const totals: Record<string, { revenue: number; storeShare: number }> = {};
    products.value.forEach(product => {
        if (!totals[product.category]) {
            totals[product.category] = { revenue: 0, storeShare: 0 };
        }
        totals[product.category].revenue += product.revenue;
        totals[product.category].storeShare += product.storeShare;
    });
    return totals;
});

// Compute total revenue
const totalRevenue = computed(() => {
    return products.value.reduce((total, product) => total + product.revenue, 0);
});

// Compute total store share
const totalStoreShare = computed(() => {
    return products.value.reduce((total, product) => total + product.storeShare, 0);
});

// Compute total revenue for the owner
const totalOwnerRevenue = computed(() => {
    return products.value.reduce((total, product) => total + product.ownerMargin, 0);
});
</script>