<template>
  <UContainer>
    <section class="bg-gray-50 py-8 antialiased dark:bg-gray-900 md:py-12">
      <div class="mx-auto max-w-screen-xl px-4 2xl:px-0">
        <!-- Heading & Filters -->
        <div class="mb-4 items-end justify-between space-y-4 sm:flex sm:space-y-0 md:mb-8">
          <div>
            <nav class="flex"
              aria-label="Breadcrumb">
              <ol class="inline-flex items-center space-x-1 md:space-x-2 rtl:space-x-reverse">
                <li class="inline-flex items-center">
                  <a href="#"
                    class="inline-flex items-center text-sm font-medium text-gray-700 hover:text-primary-600 dark:text-gray-400 dark:hover:text-white">
                    <svg class="me-2.5 h-3 w-3"
                      aria-hidden="true"
                      xmlns="http://www.w3.org/2000/svg"
                      fill="currentColor"
                      viewBox="0 0 20 20">
                      <path
                        d="m19.707 9.293-2-2-7-7a1 1 0 0 0-1.414 0l-7 7-2 2a1 1 0 0 0 1.414 1.414L2 10.414V18a2 2 0 0 0 2 2h3a1 1 0 0 0 1-1v-4a1 1 0 0 1 1-1h2a1 1 0 0 1 1 1v4a1 1 0 0 0 1 1h3a2 2 0 0 0 2-2v-7.586l.293.293a1 1 0 0 0 1.414-1.414Z" />
                    </svg>
                    Home
                  </a>
                </li>
                <li>
                  <div class="flex items-center">
                    <svg class="h-5 w-5 text-gray-400 rtl:rotate-180"
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
                    <a href="#"
                      class="ms-1 text-sm font-medium text-gray-700 hover:text-primary-600 dark:text-gray-400 dark:hover:text-white md:ms-2">สินค้าทั้งหมด</a>
                  </div>
                </li>
              </ol>
            </nav>
            <h2 class="mt-3 text-xl font-semibold text-gray-900 dark:text-white sm:text-2xl">สินค้าทั้งหมด
            </h2>

          </div>
        </div>
        <div class="mb-4 grid gap-4 sm:grid-cols-2 md:mb-8 lg:grid-cols-3 xl:grid-cols-4">

          <div v-for="product in products"
            :key="product.id"
            class="rounded-lg border border-gray-200 bg-white p-6 shadow-sm dark:border-gray-700 dark:bg-gray-800">
            <div class="h-56 w-full flex items-center justify-center">
              <a href="#">
                <img :src="product.icon"
                  :alt="product.name"
                  class="h-50 w-50 object-contain" />
              </a>
            </div>
            <div class="pt-6">
              <div class="mb-4 flex items-center justify-between gap-4">
                <span v-if="product.discount"
                  class="me-2 rounded bg-primary-100 px-2.5 py-0.5 text-xs font-medium text-primary-800 dark:bg-primary-900 dark:text-primary-300">
                  {{ product.discount }}
                </span>
                <div class="flex items-center justify-end gap-1">
                  <button type="button"
                    class="rounded-lg p-2 text-gray-500 hover:bg-gray-100 hover:text-gray-900 dark:text-gray-400 dark:hover:bg-gray-700 dark:hover:text-white">
                    <span class="sr-only">Quick look</span>
                    <svg class="h-5 w-5"
                      aria-hidden="true"
                      xmlns="http://www.w3.org/2000/svg"
                      width="24"
                      height="24"
                      fill="none"
                      viewBox="0 0 24 24">
                      <path stroke="currentColor"
                        stroke-width="2"
                        d="M21 12c0 1.2-4.03 6-9 6s-9-4.8-9-6c0-1.2 4.03-6 9-6s9 4.8 9 6Z" />
                      <path stroke="currentColor"
                        stroke-width="2"
                        d="M15 12a3 3 0 1 1-6 0 3 3 0 0 1 6 0Z" />
                    </svg>
                  </button>
                  <button type="button"
                    class="rounded-lg p-2 text-gray-500 hover:bg-gray-100 hover:text-gray-900 dark:text-gray-400 dark:hover:bg-gray-700 dark:hover:text-white">
                    <span class="sr-only">Add to Favorites</span>
                    <svg class="h-5 w-5"
                      aria-hidden="true"
                      xmlns="http://www.w3.org/2000/svg"
                      fill="none"
                      viewBox="0 0 24 24">
                      <path stroke="currentColor"
                        stroke-linecap="round"
                        stroke-linejoin="round"
                        stroke-width="2"
                        d="M12 6C6.5 1 1 8 5.8 13l6.2 7 6.2-7C23 8 17.5 1 12 6Z" />
                    </svg>
                  </button>
                </div>
              </div>
              <a href="#"
                class="text-lg font-semibold leading-tight text-gray-900 hover:underline dark:text-white">{{
                  product.name }}</a>
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
                <p class="text-sm font-medium text-gray-500 dark:text-gray-400">({{ product.reviews }})
                </p>
              </div>
              <ul class="mt-2 flex items-center gap-4">
                <li v-if="product.bestSeller"
                  class="flex items-center gap-2">
                  <svg class="h-4 w-4 text-gray-500 dark:text-gray-400"
                    aria-hidden="true"
                    xmlns="http://www.w3.org/2000/svg"
                    fill="none"
                    viewBox="0 0 24 24">
                    <path stroke="currentColor"
                      stroke-linecap="round"
                      stroke-linejoin="round"
                      stroke-width="2"
                      d="M7.171 12.906-2.153 6.411 2.672-.89 1.568 2.34 1.825-5.183m5.73-2.678 2.154 6.411-2.673-.89-1.568 2.34-1.825-5.183M9.165 4.3c.58.068 1.153-.17 1.515-.628a1.681 1.681 0 0 1 2.64 0 1.68 1.68 0 0 0 1.515.628 1.681 1.681 0 0 1 1.866 1.866c-.068.58.17 1.154.628 1.516a1.681 1.681 0 0 1 0 2.639 1.682 1.682 0 0 0-.628 1.515 1.681 1.681 0 0 1-1.866 1.866 1.681 1.681 0 0 0-1.516.628 1.681 1.681 0 0 1-2.639 0 1.681 1.681 0 0 0-1.515-.628 1.681 1.681 0 0 1-1.867-1.866 1.681 1.681 0 0 0-.627-1.515 1.681 1.681 0 0 1 0-2.64c.458-.361.696-.935.627-1.515A1.681 1.681 0 0 1 9.165 4.3ZM14 9a2 2 0 1 1-4 0 2 2 0 0 1 4 0Z" />
                  </svg>
                  <p class="text-sm font-medium text-gray-500 dark:text-gray-400">Best Seller</p>
                </li>
                <li v-if="product.bestPrice"
                  class="flex items-center gap-2">
                  <svg class="h-4 w-4 text-gray-500 dark:text-gray-400"
                    aria-hidden="true"
                    xmlns="http://www.w3.org/2000/svg"
                    fill="none"
                    viewBox="0 0 24 24">
                    <path stroke="currentColor"
                      stroke-linecap="round"
                      stroke-width="2"
                      d="M8 7V6c0-.6.4-1 1-1h11c.6 0 1 .4 1 1v7c0 .6-.4 1-1 1h-1M3 18v-7c0-.6.4-1 1-1h11c.6 0 1 .4 1 1v7c0 .6-.4 1-1 1H4a1 1 0 0 1-1-1Zm8-3.5a1.5 1.5 0 1 1-3 0 1.5 1.5 0 0 1 3 0Z" />
                  </svg>
                  <p class="text-sm font-medium text-gray-500 dark:text-gray-400">Best Price</p>
                </li>

              </ul>
              <div class="mt-4 flex items-center justify-between gap-4">
                <p class="text-2xl font-extrabold leading-tight text-gray-900 dark:text-white">{{
                  product.price }}</p>
                <UButton to="/ecommerce/orderproduct"
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
                      d="M4 4h1.5L8 16m0 0h8m-8 0a2 2 0 1 0 0 4 2 2 0 0 0 0-4Zm8 0a2 2 0 1 0 0 4 2 2 0 0 0 0-4Zm.75-3H7.5M11 7H6.312M17 4v6m-3-3h6" />
                  </svg>
                  สั่งสินค้า
                </UButton>
              </div>
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
import { ref } from 'vue';

// Define your reactive variables
const products = ref([
  {
    id: 4,
    name: 'อสังหาริมทรัพย์',
    price: '฿1,499,000',
    discount: 'Up to 10% off',
    rating: 4.9,
    reviews: 1233,
    icon: '/images/b1.jpg', // MDI: Home City
    bestSeller: true,
    bestPrice: true,
  },
  {
    id: 5,
    name: 'อาคารอยู่อาศัย 1 ชั้น',
    price: '฿999,000',
    discount: 'Up to 5% off',
    rating: 4.7,
    reviews: 856,
    icon: '/images/b2.jpg', // MDI: Home Floor 1
    bestSeller: false,
    bestPrice: true,
  },
  {
    id: 6,
    name: 'อาคารอยู่อาศัย 2 ชั้น',
    price: '฿1,299,000',
    discount: 'Up to 7% off',
    rating: 4.8,
    reviews: 1021,
    icon: '/images/b3.jpg', // MDI: Home Floor 2
    bestSeller: true,
    bestPrice: false,
  },
  {
    id: 7,
    name: 'อิฐบล็อกจิ๊กซอว์ จากเศษพืช',
    price: '฿50',
    discount: 'Up to 15% off',
    rating: 4.5,
    reviews: 200,
    icon: '/images/b4.jpg', // MDI: Cube Outline
    bestSeller: false,
    bestPrice: true,
  },
  {
    id: 8,
    name: 'อิฐบล็อกจิ๊กซอว์ จากขยะพลาสติก',
    price: '฿45',
    discount: 'Up to 10% off',
    rating: 4.6,
    reviews: 150,
    icon: '/images/b1.jpg', // MDI: Recycle
    bestSeller: true,
    bestPrice: false,
  },
  {
    id: 9,
    name: 'อิฐบล็อกจิ๊กซอว์ จากขยะ',
    price: '฿40',
    discount: 'Up to 20% off',
    rating: 4.7,
    reviews: 180,
    icon: '/images/b2.jpg', // MDI: Trash Can Outline
    bestSeller: true,
    bestPrice: true,
  },
  {
    id: 10,
    name: 'พลังงานน้ำ',
    price: '฿500,000',
    discount: 'Up to 12% off',
    rating: 4.8,
    reviews: 300,
    icon: '/images/b3.jpg', // MDI: Water
    bestSeller: true,
    bestPrice: false,
  },
  {
    id: 11,
    name: 'พลังงานลม',
    price: '฿750,000',
    discount: 'Up to 8% off',
    rating: 4.7,
    reviews: 250,
    icon: '/images/b4.jpg', // MDI: Weather Windy
    bestSeller: false,
    bestPrice: true,
  },

]);
</script>
