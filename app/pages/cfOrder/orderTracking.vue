<template>
  <UContainer>
    <section class="bg-white py-8 antialiased dark:bg-gray-900 md:py-16">
      <div class="mx-auto max-w-screen-xl px-4 2xl:px-0">
        <h2 class="text-xl font-semibold text-gray-900 dark:text-white sm:text-2xl">ติดตามการจัดส่งของใบสั่งซื้อ
          #957684673</h2>
        <div class="mt-6 sm:mt-8 lg:flex lg:gap-8">
          <div class="mt-6 grow sm:mt-8 lg:mt-0 order-1 lg:order-2">
            <div
              class="space-y-6 rounded-lg border border-gray-200 bg-white p-6 shadow-sm dark:border-gray-700 dark:bg-gray-800">
              <h3 class="text-xl font-semibold text-gray-900 dark:text-white">สถานะการจัดส่ง</h3>

              <ol class="relative ms-3 border-s border-gray-200 dark:border-gray-700">
                <li class="mb-10 ms-6">
                  <span
                    class="absolute -start-3 flex h-6 w-6 items-center justify-center rounded-full bg-gray-100 ring-8 ring-white dark:bg-gray-700 dark:ring-gray-800">
                    <svg class="h-2 w-2 text-gray-400 dark:text-gray-400"
                      xmlns="http://www.w3.org/2000/svg"
                      width="24"
                      height="24"
                      viewBox="0 0 24 24">
                      <rect width="24"
                        height="24"
                        fill="none" />
                      <path fill="currentColor"
                        d="M23.971 11.861c.28 3.888-1.527 6.094-2.615 7.636c-1.694 1.786-3.84 4.22-9.291 4.356c-4.624.183-6.896-1.85-8.804-3.617c-2.487-2.733-3.136-4.35-3.26-8.375c-.013-2.467.939-4.929 2.602-7.095C4.934 1.474 8.64.37 12.065.143c3.592-.14 6.449 1.672 8.399 3.624c2.496 2.632 3.263 4.892 3.505 8.094Z" />
                    </svg>
                  </span>
                  <h4 class="mb-0.5 text-base font-semibold text-gray-900 dark:text-white">{{ new
                    Date(Date.now() - 4 * 24 * 60 * 60 * 1000).toLocaleString('en-US', {
                      day: '2-digit',
                      month: 'short', year: 'numeric',
                    }) }}</h4>
                  <p class="text-sm font-normal text-gray-500 dark:text-gray-400">เข้ารับพัสดุแล้ว </p>

                </li>
                <li class="mb-10 ms-6">
                  <span
                    class="absolute -start-3 flex h-6 w-6 items-center justify-center rounded-full bg-gray-100 ring-8 ring-white dark:bg-gray-700 dark:ring-gray-800">
                    <svg class="h-4 w-4 text-gray-500 dark:text-gray-400"
                      xmlns="http://www.w3.org/2000/svg"
                      width="24"
                      height="24"
                      viewBox="0 0 24 24">
                      <rect width="24"
                        height="24"
                        fill="none" />
                      <g fill="none"
                        stroke="currentColor"
                        stroke-linecap="round"
                        stroke-miterlimit="10"
                        stroke-width="1.5">
                        <path d="M12 12.8a3.35 3.35 0 1 0 0-6.7a3.35 3.35 0 0 0 0 6.7Z" />
                        <path
                          d="M12 2.75c-6.7 0-7.817 5.583-6.7 9.815c.983 3.708 3.93 6.242 5.874 8.32a1.117 1.117 0 0 0 1.652 0c1.943-2.078 4.891-4.612 5.874-8.32c1.117-4.232 0-9.815-6.7-9.815Z" />
                      </g>
                    </svg>
                  </span>
                  <h4 class="mb-0.5 text-base font-semibold text-gray-900 dark:text-white">{{ new
                    Date(Date.now() - 3 * 24 * 60 * 60 * 1000).toLocaleString('en-US', {
                      day: '2-digit',
                      month: 'short', year: 'numeric',
                    }) }}</h4>
                  <p class="text-sm font-normal text-gray-500 dark:text-gray-400">
                    พัสดุจัดถึงจุดตรวจสอบศุลกากรขาออก</p>
                </li>
                <li class="mb-10 ms-6">
                  <span
                    class="absolute -start-3 flex h-6 w-6 items-center justify-center rounded-full bg-gray-100 ring-8 ring-white dark:bg-gray-700 dark:ring-gray-800">
                    <svg class="h-4 w-4 text-gray-500 dark:text-gray-400"
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
                        d="m4 12 8-8 8 8M6 10.5V19a1 1 0 0 0 1 1h3v-3a1 1 0 0 1 1-1h2a1 1 0 0 1 1 1v3h3a1 1 0 0 0 1-1v-8.5" />
                    </svg>
                  </span>
                  <h4 class="mb-0.5 text-base font-semibold text-gray-900 dark:text-white">
                    {{ new
                      Date(Date.now() - 3 * 24 * 60 * 60 * 1000).toLocaleString('en-US', {
                        day: '2-digit',
                        month: 'short', year: 'numeric',
                      }) }}</h4>
                  <p class="text-sm font-normal text-gray-500 dark:text-gray-400">
                    พัสดุถูกส่งออกจากประเทศไทย</p>

                </li>
                <li class="mb-10 ms-6">
                  <span
                    class="absolute -start-3 flex h-6 w-6 items-center justify-center rounded-full bg-gray-100 ring-8 ring-white dark:bg-gray-700 dark:ring-gray-800">
                    <svg class="h-4 w-4 text-gray-500 dark:text-gray-400"
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
                        d="M13 7h6l2 4m-8-4v8m0-8V6a1 1 0 0 0-1-1H4a1 1 0 0 0-1 1v9h2m8 0H9m4 0h2m4 0h2v-4m0 0h-5m3.5 5.5a2.5 2.5 0 1 1-5 0 2.5 2.5 0 0 1 5 0Zm-10 0a2.5 2.5 0 1 1-5 0 2.5 2.5 0 0 1 5 0Z" />
                    </svg>
                  </span>
                  <h4 class="mb-0.5 text-base font-semibold text-gray-900 dark:text-white">{{ new
                    Date(Date.now() - 2 * 24 * 60 * 60 * 1000).toLocaleString('en-US', {
                      day: '2-digit',
                      month: 'short', year: 'numeric',
                    }) }}</h4>
                  <p class="text-sm font-normal text-gray-500 dark:text-gray-400">อยู่ระหว่างการขนส่ง</p>
                </li>

                <li class="mb-10 ms-6 text-primary-700 dark:text-primary-500">
                  <span
                    class="absolute -start-3 flex h-6 w-6 items-center justify-center rounded-full bg-primary-100 ring-8 ring-white dark:bg-primary-900 dark:ring-gray-800">
                    <svg class="h-4 w-4"
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
                        d="M5 11.917 9.724 16.5 19 7.5" />
                    </svg>
                  </span>
                  <h4 class="mb-0.5 font-semibold">{{ new
                    Date(Date.now() + 0 * 24 * 60 * 60 * 1000).toLocaleString('en-US', {
                      day: '2-digit',
                      month: 'short', year: 'numeric',
                    }) }}</h4>
                  <p class="text-sm">จัดส่งสำเร็จ</p>
                </li>


              </ol>
              <div class="grid grid-cols-2 gap-4 mt-4">
                <UButton to="/cfOrder/payTheOrder"
                  class="flex justify-center"
                  color="white">ยกเลิกคำสั่งซื้อ</UButton>
                <UButton to="/cfOrder/payment"
                  class="flex justify-center">รายละเอียดการสั่งซื้อ</UButton>
              </div>
            </div>
          </div>

          <div
            class="w-full divide-y divide-gray-200 overflow-hidden rounded-lg border border-gray-200 dark:divide-gray-700 dark:border-gray-700 lg:max-w-xl xl:max-w-2xl order-2 lg:order-1">
            <div class="space-y-4 p-6"
              v-for="product in products"
              :key="product.id">
              <div class="flex items-center gap-6">
                <a href="#"
                  class="h-14 w-14 shrink-0">
                  <img class="h-full w-full dark:hidden"
                    :src="product.image"
                    :alt="product.name" />

                </a>
                <a href="#"
                  class="min-w-0 flex-1 font-medium text-gray-900 hover:underline dark:text-white">{{
                    product.name }}</a>
              </div>
              <div class="flex items-center justify-between gap-4">
                <p class="text-sm font-normal text-gray-500 dark:text-gray-400">
                  <span class="font-medium text-gray-900 dark:text-white">Product ID:</span> {{ product.id
                  }}
                </p>
                <div class="flex items-center justify-end gap-4">
                  <p class="text-base font-normal text-gray-900 dark:text-white">x{{ product.quantity }}
                  </p>
                  <p class="text-xl font-bold leading-tight text-gray-900 dark:text-white">{{
                    product.price }}</p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
  </UContainer>
</template>
<script setup lang="ts">
const products = [
  {
    id: 'BJ8364850',
    name: 'F001 กระเป๋าเดินทาง 20',
    quantity: 1,
    price: 2000,
    image: 'https://flowbite.s3.amazonaws.com/blocks/e-commerce/bag.svg',
  },
  {
    id: 'BJ8364851',
    name: 'C001 กระเป๋าเดินทาง 24',
    quantity: 1,
    price: 890,
    image: 'https://flowbite.s3.amazonaws.com/blocks/e-commerce/bag.svg',
  },
];
</script>
