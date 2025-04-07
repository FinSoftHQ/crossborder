<script setup lang="ts">
import { ref, computed, watch } from 'vue';

const isModalOpen = ref(false);
const termsAccepted = ref(false);
const orderItems = ref([
    { name: 'Apple iMac 27”', quantity: 1, price: 1499, image: 'https://flowbite.s3.amazonaws.com/blocks/e-commerce/imac-front.svg', imageDark: 'https://flowbite.s3.amazonaws.com/blocks/e-commerce/imac-front-dark.svg' },
    { name: 'Apple iPhone 14', quantity: 1, price: 1998, image: 'https://flowbite.s3.amazonaws.com/blocks/e-commerce/apple-watch-light.svg', imageDark: 'https://flowbite.s3.amazonaws.com/blocks/e-commerce/apple-watch-dark.svg' },
]);
const orderSummary = ref({
    originalPrice: ' ₿ 2,397.00',
    savings: '- ₿ 299.00',
    storePickup: '$99',
    tax: ' ₿ 799',
    total: ' ₿ 2,996.00'
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
    orderSummary.value.total = ` ₿ ${total.toFixed(2)}`;
};

// Watch for changes in orderItems and recalculate the total
watch(orderItems, calculateTotal, { deep: true });

// Initial calculation
calculateTotal();
</script>
<template>
    <UContainer>        
        <section class="bg-white py-4 antialiased dark:bg-gray-900 md:py-16">
            <h4 class="text-xl font-semibold text-gray-900 dark:text-white">จำนวนที่ต้องชำระ</h4>
            <div class="mt-4 sm:mt-4">
                <UCard>
                    <div class="mt-4 space-y-6">
                            <h4 class="text-xl text-center font-semibold border-b border-gray-200 pb-2 text-gray-900 dark:text-white">{{ orderSummary.total }}</h4>

                            <div class="space-y-4">
                                <div class="space-y-2">
                                    <dl
                                    class="flex items-center justify-between">
                                    <dt class="text-gray-500 dark:text-gray-400">ยอดรวมทั้งหมด</dt>
                                    <dd class="text-lg font-bold text-gray-900 dark:text-white">{{ orderSummary.total }}
                                    </dd>
                                </dl>
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
                            </div>                          
                                               
                        </div>
                </UCard>
                        <h4 class="text-xl font-semibold text-gray-900 dark:text-white mt-8">รายการที่สั่ง</h4>
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
                                            ` ₿ ${(item.price * item.quantity).toFixed(2)}` }}</td>
                                    </tr>
                                </tbody>
                            </table>
                        </div>            
                    </div>
                    <div class="grid grid-cols-2 gap-4 mt-4">
                            <UButton to="/coinApp/home"
                                     class="flex justify-center"
                                     color="white">ยกเลิก</UButton>
                            <UButton to="/coinApp/successpay"
                            class="flex justify-center"
                                     >ชำระเงิน</UButton>
                        </div>
        </section>

       
    </UContainer>

</template>

<style scoped>
/* Add any additional styles here */
</style>
