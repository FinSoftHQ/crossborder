<template>
    <section class="bg-white py-8 antialiased dark:bg-gray-900 md:py-16">
        <div class="mx-auto max-w-3xl px-4 sm:px-6 lg:px-8">
            <div class="mx-auto max-w-3xl">
                <h2 class="text-xl font-semibold text-gray-900 dark:text-white sm:text-2xl">รายการขายที่ขายได้</h2>
                <div class="mt-6 space-y-4 border-b border-t border-gray-200 py-8 dark:border-gray-700 sm:mt-8">
                    <h2 class="mb-4 text-xl font-bold text-gray-900 dark:text-white">รายการโรงแรมที่ขายได้</h2>
                    <table class="min-w-full divide-y divide-gray-200 dark:divide-gray-700">
                        <thead class="bg-gray-50 dark:bg-gray-800">
                            <tr>
                                <th scope="col"
                                    class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider dark:text-gray-400">
                                    ชื่อสินค้า</th>
                                <th scope="col"
                                    class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider dark:text-gray-400">
                                    ราคา</th>
                                <th scope="col"
                                    class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider dark:text-gray-400">
                                    จำนวนที่ขายได้</th>
                                <th scope="col"
                                    class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider dark:text-gray-400">
                                    ชื่อโรงแรม</th>
                            </tr>
                        </thead>
                        <tbody class="bg-white divide-y divide-gray-200 dark:bg-gray-700 dark:divide-gray-600">
                            <tr v-for="(item, index) in saleItems"
                                :key="index">
                                <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-900 dark:text-white">{{
                                    item.name }}</td>
                                <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-900 dark:text-white">{{
                                    formatCurrency(item.price) }} บาท</td>
                                <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-900 dark:text-white">{{
                                    item.quantity }}</td>
                                <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-900 dark:text-white">{{
                                    item.hotelName }}</td>
                            </tr>
                        </tbody>
                    </table>
                    <div class="mt-4">
                        <p class="text-lg font-semibold text-gray-900 dark:text-white">
                            รวมยอดขายทั้งหมด: {{ formatCurrency(totalSales) }} บาท
                        </p>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup lang="ts">
import { ref, computed } from 'vue';

const saleItems = ref([
    { name: "ห้องพัก Deluxe", price: 3000, quantity: 5, hotelName: "Hilton" },
    { name: "ห้องพัก Suite", price: 5000, quantity: 2, hotelName: "Marriott" },
    { name: "บริการอาหารเช้า", price: 500, quantity: 10, hotelName: "Hilton" },
]);

const totalSales = computed(() => {
    return saleItems.value.reduce((sum, item) => sum + item.price * item.quantity, 0);
});

const formatCurrency = (value: number): string => {
    return value.toLocaleString("en-US");
};
</script>
