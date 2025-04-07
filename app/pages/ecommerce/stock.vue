<template>
    <section class="bg-white py-8 antialiased dark:bg-gray-900 md:py-16">
        <div class="mx-auto max-w-screen-xl px-4 2xl:px-0">
            <div class="mx-auto max-w-5xl">
                <div class="gap-4 lg:flex lg:items-center lg:justify-between">
                    <h2 class="text-xl font-semibold text-gray-900 dark:text-white sm:text-2xl">คลังสินค้า</h2>                       
                </div>
                <!-- Card Section -->
                <div class="grid grid-cols-1 gap-4 sm:grid-cols-2 lg:grid-cols-5 mb-8">
                    <div v-for="(total, category) in categoryTotals"
                         :key="category"
                         class="p-4 bg-white rounded-lg shadow dark:bg-white">
                        <h3 class="text-lg font-semibold text-gray-900">{{ category }}</h3>
                        <p class="mt-2 text-sm text-gray-600">จำนวนสินค้าในร้าน: <span
                                  class="font-medium text-gray-900">{{ total }}</span></p>
                    </div>
                </div>
                <div class="mt-6 flow-root sm:mt-8">
                    <div class="gap-4 lg:flex lg:items-center lg:justify-end">
                    <div class="mt-6 gap-4 space-y-4 sm:flex sm:items-center sm:space-y-0 lg:mt-0 lg:justify-end">
                        <div>
                            <label for="category-filter"
                                   class="sr-only mb-2 block text-sm font-medium text-gray-900 dark:text-white">กรองตามประเภท</label>
                            <select id="category-filter"
                                    class="block w-full rounded-lg border border-gray-300 bg-gray-50 p-2.5 text-sm text-gray-900 focus:border-primary-500 focus:ring-primary-500 dark:border-gray-600 dark:bg-gray-700 dark:text-white dark:placeholder:text-gray-400 dark:focus:border-primary-500 dark:focus:ring-primary-500 sm:w-[144px]">
                                <option selected>ทุกประเภท</option>
                                <option value="fresh-dry">สด / แห้ง</option>
                                <option value="powder">ผง</option>
                                <option value="extract">สารสกัด</option>
                                <option value="green-product">ผลิตภัณฑ์ green product (ของกิน ของใช้)</option>
                                <option value="supplement">อาหารเสริม</option>
                            </select>
                        </div>
                        <button type="button"
                                class="w-full rounded-lg bg-primary-700 px-5 py-2.5 text-sm font-medium text-white hover:bg-primary-800 focus:outline-none focus:ring-4 focus:ring-primary-300 dark:bg-primary-600 dark:hover:bg-primary-700 dark:focus:ring-primary-800 sm:w-auto">เพิ่มสินค้า</button>
                    </div>
                </div>
                    <div class="overflow-x-auto relative shadow-md sm:rounded-lg">
                        <table class="w-full text-sm text-left text-gray-500 dark:text-gray-400">
                            <thead
                                   class="text-xs text-gray-700 uppercase bg-gray-50 dark:bg-gray-700 dark:text-gray-400">
                                <tr>
                                    <th scope="col"
                                        class="px-6 py-3">รูปภาพ</th>
                                    <th scope="col"
                                        class="px-6 py-3">ชื่อสินค้า</th>
                                    <th scope="col"
                                        class="px-6 py-3">ประเภท</th>
                                    <th scope="col"
                                        class="px-6 py-3">จำนวน</th>
                                    <th scope="col"
                                        class="px-6 py-3">จำนวนร้านค้า</th>
                                </tr>
                            </thead>
                            <tbody>
                                <tr v-for="product in products"
                                    :key="product.id"
                                    class="bg-white border-b dark:bg-gray-800 dark:border-gray-700">
                                    <td class="px-6 py-4">
                                        <img :src="product.image"
                                             alt="Product Image"
                                             class="w-16 h-16 object-cover rounded">
                                    </td>
                                    <td class="px-6 py-4 font-medium text-gray-900 dark:text-white">{{ product.name }}
                                    </td>
                                    <td class="px-6 py-4">{{ product.category }}</td>
                                    <td class="px-6 py-4">{{ product.quantity }}</td>
                                    <td class="px-6 py-4">{{ product.stores }}</td>
                                </tr>
                            </tbody>
                        </table>
                    </div>
                </div>
                <nav class="mt-2 flex items-center justify-center sm:mt-8"
                     aria-label="Page navigation example">
                    <ul class="flex h-8 items-center -space-x-px text-sm">
                        <!-- Pagination controls -->
                        <li>
                            <a href="#"
                               class="ms-0 flex h-8 items-center justify-center rounded-s-lg border border-e-0 border-gray-300 bg-white px-3 leading-tight text-gray-500 hover:bg-gray-100 hover:text-gray-700 dark:border-gray-700 dark:bg-gray-800 dark:text-gray-400 dark:hover:bg-gray-700 dark:hover:text-white">
                                <span class="sr-only">Previous</span>
                                <svg class="h-4 w-4 rtl:rotate-180"
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
                                          d="m15 19-7-7 7-7" />
                                </svg>
                            </a>
                        </li>
                        <li>
                            <a href="#"
                               class="flex h-8 items-center justify-center border border-gray-300 bg-white px-3 leading-tight text-gray-500 hover:bg-gray-100 hover:text-gray-700 dark:border-gray-700 dark:bg-gray-800 dark:text-gray-400 dark:hover:bg-gray-700 dark:hover:text-white">1</a>
                        </li>
                        <li>
                            <a href="#"
                               class="flex h-8 items-center justify-center border border-gray-300 bg-white px-3 leading-tight text-gray-500 hover:bg-gray-100 hover:text-gray-700 dark:border-gray-700 dark:bg-gray-800 dark:text-gray-400 dark:hover:bg-gray-700 dark:hover:text-white">2</a>
                        </li>
                        <li>
                            <a href="#"
                               aria-current="page"
                               class="z-10 flex h-8 items-center justify-center border border-primary-300 bg-primary-50 px-3 leading-tight text-primary-600 hover:bg-primary-100 hover:text-primary-700 dark:border-gray-700 dark:bg-gray-700 dark:text-white">3</a>
                        </li>
                        <li>
                            <a href="#"
                               class="flex h-8 items-center justify-center border border-gray-300 bg-white px-3 leading-tight text-gray-500 hover:bg-gray-100 hover:text-gray-700 dark:border-gray-700 dark:bg-gray-800 dark:text-gray-400 dark:hover:bg-gray-700 dark:hover:text-white">...</a>
                        </li>
                        <li>
                            <a href="#"
                               class="flex h-8 items-center justify-center rounded-e-lg border border-gray-300 bg-white px-3 leading-tight text-gray-500 hover:bg-gray-100 hover:text-gray-700 dark:border-gray-700 dark:bg-gray-800 dark:text-gray-400 dark:hover:bg-gray-700 dark:hover:text-white">
                                <span class="sr-only">Next</span>
                                <svg class="h-4 w-4 rtl:rotate-180"
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
                                          d="m9 5 7 7-7 7" />
                                </svg>
                            </a>
                        </li>
                    </ul>
                </nav>
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
}

const products = ref<Product[]>([
    // สด / แห้ง
    { id: 1, name: "Apple", category: "สด / แห้ง", quantity: 50, image: "https://home.maefahluang.org/images/editor/apple.jpg", stores: 10 },
    { id: 2, name: "Banana", category: "สด / แห้ง", quantity: 30, image: "https://www.healthxchange.sg/sites/hexassets/Assets/food-nutrition/good-reasons-to-eat-a-banana-today.jpg", stores: 8 },
    { id: 3, name: "Cherry", category: "สด / แห้ง", quantity: 100, image: "https://upload.wikimedia.org/wikipedia/commons/f/f6/Cherry_season_%2848216568227%29.jpg", stores: 12 },

    // ผง
    { id: 4, name: "Matcha Powder", category: "ผง", quantity: 20, image: "https://i.etsystatic.com/26840043/r/il/4509f0/5299934659/il_fullxfull.5299934659_dhb7.jpg", stores: 5 },
    { id: 5, name: "Cocoa Powder", category: "ผง", quantity: 15, image: "https://cdn.shopify.com/s/files/1/0229/2203/files/cocoa_powder.png?v=1692687871", stores: 7 },
    { id: 6, name: "Turmeric Powder", category: "ผง", quantity: 25, image: "https://domf5oio6qrcr.cloudfront.net/medialibrary/15065/conversions/fa246ce0-054b-4892-bf30-5eb43cd938aa-thumb.jpg", stores: 6 },

    // สารสกัด
    { id: 7, name: "Green Tea Extract", category: "สารสกัด", quantity: 10, image: "https://www.disthai.com/images/content/original-1680925806479.jpg", stores: 4 },
    { id: 8, name: "Ginseng Extract", category: "สารสกัด", quantity: 12, image: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTdzmZQZvYGFfAcWkJAXesah4Bebn9gs32aMg&s", stores: 3 },
    { id: 9, name: "Aloe Vera Extract", category: "สารสกัด", quantity: 18, image: "https://inwfile.com/s-b/ldg7ue.jpg", stores: 5 },

    // ผลิตภัณฑ์ green product (ของกิน ของใช้)
    { id: 10, name: "Eco-Friendly Soap", category: "ผลิตภัณฑ์ (ของกิน ของใช้)", quantity: 40, image: "https://kj1bcdn.b-cdn.net/media/55090/bar.jpeg", stores: 9 },
    { id: 11, name: "Reusable Bag", category: "ผลิตภัณฑ์ (ของกิน ของใช้)", quantity: 60, image: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQlDuSgdzmKiuSiGAiK0DHMEmLXytljB5iwzg&s", stores: 15 },
    { id: 12, name: "Bamboo Toothbrush", category: "ผลิตภัณฑ์ (ของกิน ของใช้)", quantity: 35, image: "https://zerowastecartel.com/cdn/shop/products/10-pack-of-bamboo-toothbrushes-671048_1445x.jpg?v=1692183433", stores: 10 },

    // อาหารเสริม
    { id: 13, name: "Vitamin C", category: "อาหารเสริม", quantity: 50, image: "https://res.cloudinary.com/dk0z4ums3/image/upload/v1708488896/attached_image_th/%E0%B8%A7%E0%B8%B4%E0%B8%95%E0%B8%B2%E0%B8%A1%E0%B8%B4%E0%B8%99%E0%B8%8B%E0%B8%B5.jpg", stores: 20 },
]);

// Compute total products in stores by category
const categoryTotals = computed(() => {
    const totals: Record<string, number> = {};
    products.value.forEach(product => {
        if (!totals[product.category]) {
            totals[product.category] = 0;
        }
        totals[product.category] += product.stores;
    });
    return totals;
});
</script>