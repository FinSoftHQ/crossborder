<template>
    <UContainer>
        <section class="bg-white py-8 antialiased dark:bg-gray-900 md:py-16">
            <form @submit.prevent="submitOrder"
                  class="mx-auto max-w-screen-xl px-4 2xl:px-0">
                <div class="mx-auto max-w-3xl">
                    <h2 class="text-xl font-semibold text-gray-900 dark:text-white sm:text-2xl">สินค้ารวมทั้งหมด</h2>

                    <div class="mt-6 space-y-4 border-b border-t border-gray-200 py-8 dark:border-gray-700 sm:mt-8">
                        <h4 class="text-lg font-semibold text-gray-900 dark:text-white">ข้อมูลการจัดส่ง</h4>

                        <dl>
                            <dt class="text-base font-medium text-gray-900 dark:text-white">Somchai Sittipong</dt>
                            <dd class="mt-1 text-base font-normal text-gray-500 dark:text-gray-400">
                                Lao PDR, Vientiane, 1234, Lane Xang Avenue
                            </dd>
                            <br />
                        </dl>

                        <button type="button"
                                @click="toggleModal"
                                class="text-base font-medium text-primary-700 hover:underline dark:text-primary-500">แก้ไข</button>
                    </div>

                    <div class="mt-6 sm:mt-8">
                        <h4 class="text-xl font-semibold text-gray-900 dark:text-white">จำนวนสินค้าทั้งหมด {{
                            orderItems.length }}</h4>


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
                                            `₿ ${(item.price *
                                                item.quantity).toFixed(2).replace(/\B(?=(\d{3})+(?!\d))/g, ',')}` }}</td>
                                    </tr>
                                </tbody>
                            </table>
                        </div>
                        <!-- ช่องทางชำระเงิน -->
                        <div class="space-y-4 mt-8">
                            <h3 class="text-xl font-semibold text-gray-900 dark:text-white">ช่องทางชำระเงิน</h3>

                            <div class="grid grid-cols-1 gap-4 md:grid-cols-1">
                                <div
                                     class="rounded-lg border border-gray-200 bg-gray-50 p-4 ps-4 dark:border-gray-700 dark:bg-gray-800">
                                    <div class="flex items-start">
                                        <div class="flex h-5 items-center">
                                            <input id="credit-card"
                                                   aria-describedby="credit-card-text"
                                                   type="radio"
                                                   name="payment-method"
                                                   value=""
                                                   class="h-4 w-4 border-gray-300 bg-white text-primary-600 focus:ring-2 focus:ring-primary-600 dark:border-gray-600 dark:bg-gray-700 dark:ring-offset-gray-800 dark:focus:ring-primary-600"
                                                   checked />
                                        </div>

                                        <div class="ms-4 text-sm">
                                            <label for="credit-card"
                                                   class="font-medium leading-none text-gray-900 dark:text-white">
                                                KGO Coin</label>
                                            <p id="credit-card-text"
                                               class="mt-1 text-xs font-normal text-gray-500 dark:text-gray-400">จ่าย
                                                ด้วยเหรียญในกระเป๋าของคุณ</p>
                                        </div>
                                    </div>

                                    <!-- <div class="mt-4 flex items-center gap-2">
                                        <button type="button"
                                                class="text-sm font-medium text-gray-500 hover:text-gray-900 dark:text-gray-400 dark:hover:text-white">Delete</button>

                                        <div class="h-3 w-px shrink-0 bg-gray-200 dark:bg-gray-700"></div>

                                        <button type="button"
                                                class="text-sm font-medium text-gray-500 hover:text-gray-900 dark:text-gray-400 dark:hover:text-white">Edit</button>
                                    </div> -->
                                </div>

                                <div
                                     class="rounded-lg border border-gray-200 bg-gray-50 p-4 ps-4 dark:border-gray-700 dark:bg-gray-800">
                                    <div class="flex items-start">
                                        <div class="flex h-5 items-center">
                                            <input id="pay-on-delivery"
                                                   aria-describedby="pay-on-delivery-text"
                                                   type="radio"
                                                   name="payment-method"
                                                   value=""
                                                   class="h-4 w-4 border-gray-300 bg-white text-primary-600 focus:ring-2 focus:ring-primary-600 dark:border-gray-600 dark:bg-gray-700 dark:ring-offset-gray-800 dark:focus:ring-primary-600" />
                                        </div>

                                        <div class="ms-4 text-sm">
                                            <label for="pay-on-delivery"
                                                   class="font-medium leading-none text-gray-900 dark:text-white">
                                                ธนาคาร </label>
                                            <p id="pay-on-delivery-text"
                                               class="mt-1 text-xs font-normal text-gray-500 dark:text-gray-400">
                                                ชำระผ่านแอปพลิเคชันธนาคาร</p>
                                        </div>
                                    </div>

                                </div>

                                <div
                                     class="rounded-lg border border-gray-200 bg-gray-50 p-4 ps-4 dark:border-gray-700 dark:bg-gray-800">
                                    <div class="flex items-start">
                                        <div class="flex h-5 items-center">
                                            <input id="paypal-2"
                                                   aria-describedby="paypal-text"
                                                   type="radio"
                                                   name="payment-method"
                                                   value=""
                                                   class="h-4 w-4 border-gray-300 bg-white text-primary-600 focus:ring-2 focus:ring-primary-600 dark:border-gray-600 dark:bg-gray-700 dark:ring-offset-gray-800 dark:focus:ring-primary-600" />
                                        </div>

                                        <div class="ms-4 text-sm">
                                            <label for="paypal-2"
                                                   class="font-medium leading-none text-gray-900 dark:text-white">
                                                QR Promptpay </label>
                                            <p id="paypal-text"
                                               class="mt-1 text-xs font-normal text-gray-500 dark:text-gray-400">
                                                ชำระเงินด้วยการสแกน QR Code</p>
                                        </div>
                                    </div>


                                </div>
                            </div>
                        </div>
                        <div>
                            <label for="voucher"
                                   class="mt-4 mb-2 block text-sm font-medium text-gray-900 dark:text-white">
                                เพิ่มโค้ดส่วนลด </label>
                            <div class="flex max-w-md items-center gap-4">
                                <input type="text"
                                       id="voucher"
                                       class="block w-full rounded-lg border border-gray-300 bg-gray-50 p-2.5 text-sm text-gray-900 focus:border-primary-500 focus:ring-primary-500 dark:border-gray-600 dark:bg-gray-700 dark:text-white dark:placeholder:text-gray-400 dark:focus:border-primary-500 dark:focus:ring-primary-500"
                                       placeholder=""
                                       required />
                                <button type="button"
                                        class="flex items-center justify-center rounded-lg bg-primary-700 px-5 py-2.5 text-sm font-medium text-white hover:bg-primary-800 focus:outline-none focus:ring-4 focus:ring-primary-300 dark:bg-primary-600 dark:hover:bg-primary-700 dark:focus:ring-primary-800">ตกลง</button>
                            </div>
                        </div>

                        <div class="mt-4 space-y-6">
                            <h4 class="text-xl font-semibold text-gray-900 dark:text-white">ข้อมูลการชำระเงิน</h4>

                            <div class="space-y-4">
                                <div class="space-y-2">
                                    <dl class="flex items-center justify-between gap-4">
                                        <dt class="text-gray-500 dark:text-gray-400">รายการสั่งสินค้า</dt>
                                        <dd class="text-base font-medium text-gray-900 dark:text-white">{{
                                            orderSummary.originalPrice }}</dd>
                                    </dl>

                                    <dl class="flex items-center justify-between gap-4">
                                        <dt class="text-gray-500 dark:text-gray-400">ส่วนลด</dt>
                                        <dd class="text-base font-medium text-green-500">{{ orderSummary.savings }}</dd>
                                    </dl>

                                    <dl class="flex items-center justify-between gap-4">
                                        <dt class="text-gray-500 dark:text-gray-400">การจัดส่ง</dt>
                                        <dd class="text-base font-medium text-gray-900 dark:text-white">{{
                                            orderSummary.storePickup }}</dd>
                                    </dl>

                                    <dl class="flex items-center justify-between gap-4">
                                        <dt class="text-gray-500 dark:text-gray-400">Tax</dt>
                                        <dd class="text-base font-medium text-gray-900 dark:text-white">{{
                                            orderSummary.tax
                                            }}</dd>
                                    </dl>
                                </div>

                                <dl
                                    class="flex items-center justify-between gap-4 border-t border-gray-200 pt-2 dark:border-gray-700">
                                    <dt class="text-lg font-bold text-gray-900 dark:text-white">ยอดรวมทั้งหมด</dt>
                                    <dd class="text-lg font-bold text-gray-900 dark:text-white">{{ orderSummary.total }}
                                    </dd>
                                </dl>
                            </div>
                            <!--
                        <div class="flex items-start sm:items-center">
                            <input id="terms-checkbox-2"
                                   type="checkbox"
                                   v-model="termsAccepted"
                                   class="h-4 w-4 rounded border-gray-300 bg-gray-100 text-primary-600 focus:ring-2 focus:ring-primary-500 dark:border-gray-600 dark:bg-gray-700 dark:ring-offset-gray-800 dark:focus:ring-primary-600" />
                            <label for="terms-checkbox-2"
                                   class="ms-2 text-sm font-medium text-gray-900 dark:text-gray-300">
                                I agree with the <a href="#"
                                   title=""
                                   class="text-primary-700 underline hover:no-underline dark:text-primary-500">Terms and
                                    Conditions</a> of use of the Flowbite marketplace
                            </label>
                        </div> -->

                            <div class="grid grid-cols-2 gap-4">
                                <UButton to="/"
                                         class="flex w-full items-center justify-center rounded-lg  border border-gray-200 bg-white px-5  py-2.5 text-sm font-medium text-gray-900 hover:bg-gray-100 hover:text-primary-700 focus:z-10 focus:outline-none focus:ring-4 focus:ring-gray-100 dark:border-gray-600 dark:bg-gray-800 dark:text-gray-400 dark:hover:bg-gray-700 dark:hover:text-white dark:focus:ring-gray-700">
                                    กลับไปยังหน้าสินค้า
                                </UButton>
                                <UButton to="/prototype/payment"
                                         class="flex w-full items-center justify-center rounded-lg bg-primary-700  px-5 py-2.5 text-sm font-medium text-white hover:bg-primary-800 focus:outline-none focus:ring-4 focus:ring-primary-300  dark:bg-primary-600 dark:hover:bg-primary-700 dark:focus:ring-primary-800 sm:mt-0">
                                    สั่งสินค้า
                                </UButton>
                            </div>
                        </div>
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
    { name: 'Apple iMac 27”', quantity: 1, price: 1499, image: 'https://flowbite.s3.amazonaws.com/blocks/e-commerce/imac-front.svg', imageDark: 'https://flowbite.s3.amazonaws.com/blocks/e-commerce/imac-front-dark.svg' },
    { name: 'Apple iPhone 14', quantity: 1, price: 1998, image: 'https://flowbite.s3.amazonaws.com/blocks/e-commerce/apple-watch-light.svg', imageDark: 'https://flowbite.s3.amazonaws.com/blocks/e-commerce/apple-watch-dark.svg' },
]);
const orderSummary = ref({
    originalPrice: '₿ 2,397.00',
    savings: '₿ 299.00',
    storePickup: '₿ 99',
    tax: '₿  799',
    total: '₿ 2,996.00'
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
    orderSummary.value.total = `₿${total.toFixed(2).replace(/\B(?=(\d{3})+(?!\d))/g, ',')}`;
};


// Watch for changes in orderItems and recalculate the total
watch(orderItems, calculateTotal, { deep: true });

// Initial calculation
calculateTotal();
</script>
<style scoped>
/* Add any additional styles here */
</style>
