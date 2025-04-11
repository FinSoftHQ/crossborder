<template>
  <UContainer>
    <section class="bg-white py-8 antialiased dark:bg-gray-900 md:py-16">
      <div class="mx-auto max-w-screen-xl px-4 2xl:px-0">
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
                <li aria-current="page">
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
                    <span
                          class="ms-1 text-sm font-medium text-gray-500 dark:text-gray-400 md:ms-2">รายการที่ต้องการสั่งซื้อ</span>
                  </div>
                </li>
              </ol>
            </nav>
            <h2 class="mt-3 text-xl font-semibold text-gray-900 dark:text-white sm:text-2xl">รายการที่ต้องการสั่งซื้อ
            </h2>

          </div>
        </div>
        <div class="mt-6 sm:mt-8 md:gap-6 lg:flex lg:items-start xl:gap-8">
          <div class="mx-auto w-full flex-none lg:max-w-2xl xl:max-w-4xl">
            <div class="space-y-6">
              <div v-for="product in products"
                   :key="product.id"
                   class="rounded-lg border border-gray-200 bg-white p-4 shadow-sm dark:border-gray-700 dark:bg-gray-800 md:p-6">
                <div class="space-y-4 md:flex md:items-center md:justify-between md:gap-6 md:space-y-0">
                  <div>
                    <input v-model="product.selected"
                           :id="product.id"
                           type="checkbox"
                           class="h-4 w-4 rounded border-gray-300 bg-gray-100 text-primary-700 focus:ring-2 focus:ring-primary-500 dark:border-gray-600 dark:bg-gray-700 dark:ring-offset-gray-800 dark:focus:ring-primary-600" />
                    <label :for="product.id"
                           class="sr-only"> {{ product.name }} </label>
                  </div>
                  <a href="#"
                     class="shrink-0 md:order-1">
                    <img class="h-20 w-20 dark:hidden"
                         :src="product.imageLight"
                         :alt="product.name" />
                  </a>
                  <label for="counter-input"
                         class="sr-only">Choose quantity:</label>
                  <div class="flex items-center justify-between md:order-3 md:justify-end">
                    <div class="flex items-center">
                      <button type="button"
                              @click="decrementQuantity(product.id)"
                              class="inline-flex h-5 w-5 shrink-0 items-center justify-center rounded-md border border-gray-300 bg-gray-100 hover:bg-gray-200 focus:outline-none focus:ring-2 focus:ring-gray-100 dark:border-gray-600 dark:bg-gray-700 dark:hover:bg-gray-600 dark:focus:ring-gray-700">
                        <svg class="h-2.5 w-2.5 text-gray-900 dark:text-white"
                             aria-hidden="true"
                             xmlns="http://www.w3.org/2000/svg"
                             fill="none"
                             viewBox="0 0 18 2">
                          <path stroke="currentColor"
                                stroke-linecap="round"
                                stroke-linejoin="round"
                                stroke-width="2"
                                d="M1 1h16" />
                        </svg>
                      </button>
                      <input type="text"
                             :value="product.quantity"
                             class="w-10 shrink-0 border-0 bg-transparent text-center text-sm font-medium text-gray-900 focus:outline-none focus:ring-0 dark:text-white"
                             readonly />
                      <button type="button"
                              @click="incrementQuantity(product.id)"
                              class="inline-flex h-5 w-5 shrink-0 items-center justify-center rounded-md border border-gray-300 bg-gray-100 hover:bg-gray-200 focus:outline-none focus:ring-2 focus:ring-gray-100 dark:border-gray-600 dark:bg-gray-700 dark:hover:bg-gray-600 dark:focus:ring-gray-700">
                        <svg class="h-2.5 w-2.5 text-gray-900 dark:text-white"
                             aria-hidden="true"
                             xmlns="http://www.w3.org/2000/svg"
                             fill="none"
                             viewBox="0 0 18 18">
                          <path stroke="currentColor"
                                stroke-linecap="round"
                                stroke-linejoin="round"
                                stroke-width="2"
                                d="M9 1v16M1 9h16" />
                        </svg>
                      </button>
                    </div>
                    <div class="text-end md:order-4 md:w-32">
                      <p class="text-base font-bold text-gray-900 dark:text-white">₿ {{ product.price *
                        product.quantity }}</p>
                    </div>
                  </div>
                  <div class="w-full min-w-0 flex-1 space-y-4 md:order-2 md:max-w-md">
                    <a href="#"
                       class="text-base font-medium text-gray-900 hover:underline dark:text-white">{{
                        product.name }}</a>
                    <div class="flex items-center gap-4">
                      <button type="button"
                              class="inline-flex items-center text-sm font-medium text-gray-500 hover:text-gray-900 hover:underline dark:text-gray-400 dark:hover:text-white">
                        <svg class="me-1.5 h-5 w-5"
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
                                d="M12.01 6.001C6.5 1 1 8 5.782 13.001L12.011 20l6.23-7C23 8 17.5 1 12.01 6.002Z" />
                        </svg>
                        Add to Favorites
                      </button>
                      <button type="button"
                              @click="removeProduct(product.id)"
                              class="inline-flex items-center text-sm font-medium text-red-600 hover:underline dark:text-red-500">
                        <svg class="me-1.5 h-5 w-5"
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
                                d="M6 18 17.94 6M18 18 6.06 6" />
                        </svg>
                        Remove
                      </button>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>

          <div class="mx-auto mt-6 max-w-4xl flex-1 space-y-6 lg:mt-0 lg:w-full">
            <div
                 class="space-y-4 rounded-lg border border-gray-200 bg-white p-4 shadow-sm dark:border-gray-700 dark:bg-gray-800 sm:p-6">
              <p class="text-xl font-semibold text-gray-900 dark:text-white">ข้อมูลการชำระเงิน</p>

              <div class="space-y-4">
                <div class="space-y-2">
                  <dl class="flex items-center justify-between gap-4">
                    <dt class="text-base font-normal text-gray-500 dark:text-gray-400">รายการสั่งสินค้า
                    </dt>
                    <dd class="text-base font-medium text-gray-900 dark:text-white">₿ {{ totalPrice }}
                    </dd>
                  </dl>

                  <dl class="flex items-center justify-between gap-4">
                    <dt class="text-base font-normal text-gray-500 dark:text-gray-400">ส่วนลด</dt>
                    <dd class="text-base font-medium text-green-600">-₿ 0.00</dd> <!-- Changed to 0 -->
                  </dl>

                  <dl class="flex items-center justify-between gap-4">
                    <dt class="text-base font-normal text-gray-500 dark:text-gray-400">การจัดส่ง</dt>
                    <dd class="text-base font-medium text-gray-900 dark:text-white">₿ 120</dd> <!-- Updated to 120 -->
                  </dl>

                  <dl class="flex items-center justify-between gap-4">
                    <dt class="text-base font-normal text-gray-500 dark:text-gray-400">Tax</dt>
                    <dd class="text-base font-medium text-gray-900 dark:text-white">₿ 0</dd> <!-- Updated to 0 -->
                  </dl>
                </div>

                <dl class="flex items-center justify-between gap-4 border-t border-gray-200 pt-2 dark:border-gray-700">
                  <dt class="text-base font-bold text-gray-900 dark:text-white">ยอดรวมทั้งหมด</dt>
                  <dd class="text-base font-bold text-gray-900 dark:text-white">₿ {{ finalTotal.toLocaleString() }}</dd>
                  <!-- Updated to use finalTotal -->
                </dl>
              </div>

              <UButton to="/ecommerce/orderSummary2"
                       class="flex w-full items-center justify-center rounded-lg bg-primary-700 px-5 py-2.5 text-sm font-medium text-white hover:bg-primary-800 focus:outline-none focus:ring-4 focus:ring-primary-300 dark:bg-primary-600 dark:hover:bg-primary-700 dark:focus:ring-primary-800">
                ดำเนินการชำระเงิน
              </UButton>

            </div>

            <!-- <div
                             class="space-y-4 rounded-lg border border-gray-200 bg-white p-4 shadow-sm dark:border-gray-700 dark:bg-gray-800 sm:p-6">
                            <form class="space-y-4">
                                <div>
                                    <label for="voucher"
                                           class="mb-2 block text-sm font-medium text-gray-900 dark:text-white"> Do you have
                                        a voucher or gift card? </label>
                                    <input type="text"
                                           id="voucher"
                                           class="block w-full rounded-lg border border-gray-300 bg-gray-50 p-2.5 text-sm text-gray-900 focus:border-primary-500 focus:ring-primary-500 dark:border-gray-600 dark:bg-gray-700 dark:text-white dark:placeholder:text-gray-400 dark:focus:border-primary-500 dark:focus:ring-primary-500"
                                           placeholder=""
                                           required />
                                </div>
                                <button type="submit"
                                        class="flex w-full items-center justify-center rounded-lg bg-primary-700 px-5 py-2.5 text-sm font-medium text-white hover:bg-primary-800 focus:outline-none focus:ring-4 focus:ring-primary-300 dark:bg-primary-600 dark:hover:bg-primary-700 dark:focus:ring-primary-800">Apply
                                    Code</button>
                            </form>
                        </div> -->
          </div>
        </div>
      </div>
    </section>
  </UContainer>
</template>
<script setup lang="ts">
import { ref, computed } from 'vue';

const products = ref([
  {
    id: 1,
    name: 'Apple',
    price: 120,
    rating: 4.8,
    reviews: 'สด / แห้ง',
    weight: '100 kg',
    imageLight: 'https://home.maefahluang.org/images/editor/apple.jpg',
    quantity: 1, // Added
    selected: true, // Added
  },
  {
    id: 2,
    name: 'Banana',
    price: 50,
    reviews: 'สด / แห้ง',
    weight: '100 kg',
    imageLight: 'https://fit-d.com/uploads/food/5f6c8c69a8f190b979f93f02475aac80.jpg',
    quantity: 1, // Added
    selected: true, // Added
  },
]);

const incrementQuantity = (productId: number) => { // Changed type to number
  const product = products.value.find((product) => product.id === productId);
  if (product) {
    product.quantity++;
  }
};

const decrementQuantity = (productId: number) => { // Changed type to number
  const product = products.value.find((product) => product.id === productId);
  if (product && product.quantity > 1) {
    product.quantity--;
  }
};

const removeProduct = (productId: number) => { // Changed type to number
  products.value = products.value.filter((product) => product.id !== productId);
};

const totalPrice = computed(() => {
  return products.value.reduce((total, product) => {
    return product.selected ? total + product.price * product.quantity : total;
  }, 0);
});

const shippingCost = 120; // Added shipping cost

const finalTotal = computed(() => {
  return totalPrice.value + shippingCost; // Includes shipping cost
});
</script>
