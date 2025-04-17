<template>
  <UContainer>
      <section class="bg-white py-8 antialiased dark:bg-gray-900 md:py-16">
          <form @submit.prevent="submitOrder"
                class="mx-auto max-w-screen-xl px-4 2xl:px-0">
              <div class="mx-auto max-w-3xl">
                  <h2 class="text-xl font-semibold text-gray-900 dark:text-white sm:text-2xl">รายละเอียดคำสั่งซื้อ</h2>

                  <div class="mt-6 space-y-4 border-b border-t border-gray-200 py-8 dark:border-gray-700 sm:mt-8">
                      <h4 class="text-lg font-semibold text-gray-900 dark:text-white">ข้อมูลสถานที่รับสินค้า</h4>

                      <dl>
                          <dt class="text-base font-medium text-gray-900 dark:text-white">สวนผลไม้สุขใจ</dt>
                          <dd class="mt-1 text-base font-normal text-gray-500 dark:text-gray-400">
                              1234, ถนนสุขใจ, ตำบลสวนผลไม้, อำเภอเมือง, จังหวัดเลย, ประเทศไทย
                          </dd>
                          <br />
                      </dl>


                  </div>

                  <div class="mt-6 sm:mt-8">
                      <h4 class="text-xl font-semibold text-gray-900 dark:text-white">จำนวนสินค้าที่ต้องจัดส่งทั้งหมด {{
                          orderItems.length }} รายการ</h4>


                      <div class="relative overflow-x-auto border-b border-gray-200 dark:border-gray-800">
                          <table class="w-full text-left font-medium text-gray-900 dark:text-white md:table-fixed">
                              <tbody class="divide-y divide-gray-200 dark:divide-gray-800">
                                  <tr v-for="item in orderItems"
                                      :key="item.name">
                                      <td class="whitespace-nowrap py-4 md:w-[384px]">
                                          <div class="flex items-center gap-4">
                                              <a href="#"
                                                 class="flex items-center aspect-square w-10 h-10 shrink-0">
                                                  <img :src="item.image"
                                                       :alt="item.name"
                                                       class="h-auto w-full max-h-full dark:hidden" />
                                                  <img :src="item.imageDark"
                                                       :alt="item.name"
                                                       class="hidden h-auto w-full max-h-full dark:block" />
                                              </a>
                                              <a href="#"
                                                 class="hover:underline">{{ item.name }}</a>
                                          </div>
                                      </td>
                                      <td class="p-4 text-base font-normal text-gray-900 dark:text-white">{{
                                          item.quantity
                                      }}</td>
                                      <td class="p-4 text-right text-base font-bold text-gray-900 dark:text-white">{{
                                          `฿ ${(item.price *
                                              item.quantity).toFixed(2).replace(/\B(?=(\d{3})+(?!\d))/g, ',')}` }}</td>
                                  </tr>
                              </tbody>
                          </table>
                          <dl
                                    class="flex items-center justify-between gap-4 border-t border-gray-200 pt-8 dark:border-gray-700">
                                    <dt class="text-lg font-bold text-gray-900 dark:text-white">ยอดรวมทั้งหมด</dt>
                                    <dd class="text-lg font-bold text-gray-900 dark:text-white">{{ orderSummary.total }}
                                    </dd>
                                </dl>
                      </div>
                      <!-- ช่องทางชำระเงิน -->


                  </div>
              </div>
          </form>
      </section>

      <div v-if="isModalOpen"
           id="billingInformationModal"
           tabindex="-1"
           aria-hidden="true"
           class="antialiased fixed left-0 right-0 top-0 z-50 flex h-[calc(100%-1rem)] max-h-auto w-full max-h-full items-center justify-center overflow-y-auto overflow-x-hidden antialiased md:inset-0">
          <div class="relative max-h-auto w-full max-h-full max-w-lg p-4">
              <div class="relative rounded-lg bg-white shadow dark:bg-gray-800">
                  <div
                       class="flex items-center justify-between rounded-t border-b border-gray-200 p-4 dark:border-gray-700 md:p-5">
                      <h3 class="text-lg font-semibold text-gray-900 dark:text-white">Billing Information</h3>
                      <button type="button"
                              @click="toggleModal"
                              class="ms-auto inline-flex h-8 w-8 items-center justify-center rounded-lg bg-transparent text-sm text-gray-400 hover:bg-gray-200 hover:text-gray-900 dark:hover:bg-gray-600 dark:hover:text-white">
                          <svg class="h-3 w-3"
                               aria-hidden="true"
                               xmlns="http://www.w3.org/2000/svg"
                               fill="none"
                               viewBox="0 0 14 14">
                              <path stroke="currentColor"
                                    stroke-linecap="round"
                                    stroke-linejoin="round"
                                    stroke-width="2"
                                    d="m1 1 6 6m0 0 6 6M7 7l6-6M7 7l-6 6" />
                          </svg>
                          <span class="sr-only">Close modal</span>
                      </button>
                  </div>
                  <form @submit.prevent="saveBillingInformation"
                        class="p-4 md:p-5">
                      <!-- Form content here -->
                      <div class="border-t border-gray-200 pt-4 dark:border-gray-700 md:pt-5">
                          <button type="submit"
                                  class="me-2 inline-flex items-center rounded-lg bg-primary-700 px-5 py-2.5 text-center text-sm font-medium text-white hover:bg-primary-800 focus:outline-none focus:ring-4 focus:ring-primary-300 dark:bg-primary-600 dark:hover:bg-primary-700 dark:focus:ring-primary-800">Save
                              information</button>
                          <button type="button"
                                  @click="toggleModal"
                                  class="me-2 rounded-lg border border-gray-200 bg-white px-5 py-2.5 text-sm font-medium text-gray-900 hover:bg-gray-100 hover:text-primary-700 focus:z-10 focus:outline-none focus:ring-4 focus:ring-gray-100 dark:border-gray-600 dark:bg-gray-800 dark:text-gray-400 dark:hover:bg-gray-700 dark:hover:text-white dark:focus:ring-gray-700">Cancel</button>
                      </div>
                  </form>
              </div>
          </div>
      </div>
  </UContainer>

</template>
<script setup lang="ts">
import { ref, computed, watch } from 'vue';

const isModalOpen = ref(false);
const termsAccepted = ref(false);
const orderItems = ref([
  {
      id: 1,
      name: 'Apple',
      price: 120,
      rating: 4.8,
      reviews: 'สด / แห้ง',
      weight: '100 kg',
      image: 'https://home.maefahluang.org/images/editor/apple.jpg',
      quantity: 1,
      selected: true,
  },
  {
      id: 2,
      name: 'Banana',
      price: 50,
      reviews: 'สด / แห้ง',
      weight: '100 kg',
      image: 'https://fit-d.com/uploads/food/5f6c8c69a8f190b979f93f02475aac80.jpg',
      quantity: 1,
      selected: true,
  },
]);

const orderSummary = ref({
  originalPrice: '฿ 2.00', // Updated
  savings: '฿ 0.00', // Updated
  storePickup: '฿ 0.00', // Updated
  tax: '฿ 0.00', // Updated
  total: '฿ 2.00', // Updated
});

const toggleModal = () => {
  isModalOpen.value = !isModalOpen.value;
};

const submitOrder = () => {
  if (termsAccepted.value) {
      alert('Order submitted successfully!');
  } else {
      alert('Please accept the terms and conditions.');
  }
};

const saveBillingInformation = () => {
  alert('Billing information saved successfully!');
  toggleModal();
};

const returnToShopping = () => {
  alert('Returning to shopping...');
};

const calculateTotal = () => {
  const total = orderItems.value.reduce((sum, item) => sum + item.price * item.quantity, 0);
  orderSummary.value.originalPrice = `฿${total.toFixed(2).replace(/\B(?=(\d{3})+(?!\d))/g, ',')}`;
  orderSummary.value.savings = '฿ 0.00'; // Ensure savings is 0
  orderSummary.value.storePickup = '฿ 120.00'; // Updated shipping cost
  orderSummary.value.tax = '฿ 0.00'; // Ensure tax is 0
  orderSummary.value.total = `฿${(total + 120).toFixed(2).replace(/\B(?=(\d{3})+(?!\d))/g, ',')}`; // Total includes shipping
};


// Watch for changes in orderItems and recalculate the total
watch(orderItems, calculateTotal, { deep: true });

// Initial calculation
calculateTotal();
</script>
<style scoped>
/* Add any additional styles here */
</style>
