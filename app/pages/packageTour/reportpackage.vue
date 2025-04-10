<template>
    <section class="bg-white py-8 antialiased dark:bg-gray-900 md:py-16">
        <div class="mx-auto max-w-5xl px-4 sm:px-6 lg:px-8">
            <h2 class="text-xl font-semibold text-gray-900 dark:text-white sm:text-2xl">รายงานสรุปการขายแพ็คเกจ</h2>
            <div class="mt-6 space-y-4 border-b border-t border-gray-200 py-8 dark:border-gray-700 sm:mt-8">
                <div class="flex justify-between items-center">
                    <h3 class="mb-4 text-lg font-bold text-gray-900 dark:text-white">ข้อมูลแพ็คเกจวันนี้</h3>
                    <NuxtLink to="/hotel/back/hotelRegister">
                        <button type="button"
                                class="inline-flex items-center px-5 py-2.5 mt-4 sm:mt-6 text-sm font-medium text-center text-white bg-primary-700 rounded-lg focus:ring-4 focus:ring-primary-200 dark:focus:ring-primary-900 hover:bg-primary-800">
                            เพิ่มแพ็คเกจ
                        </button>
                    </NuxtLink>
                </div>
                <table class="min-w-full divide-y divide-gray-200 dark:divide-gray-700">
                    <thead class="bg-gray-50 dark:bg-gray-800">
                        <tr>
                            <th scope="col"
                                class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider dark:text-gray-400">
                                รูปภาพ</th>
                            <th scope="col"
                                class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider dark:text-gray-400">
                                ชื่อแพ็คเกจ</th>
                            <th scope="col"
                                class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider dark:text-gray-400">
                                ราคา</th>
                            <th scope="col"
                                class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider dark:text-gray-400">
                                สถานะ</th>
                            <th scope="col"
                                class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider dark:text-gray-400">
                                การจัดการ</th>
                        </tr>
                    </thead>
                    <tbody class="bg-white divide-y divide-gray-200 dark:bg-gray-700 dark:divide-gray-600">
                        <tr v-for="room in rooms"
                            :key="room.id">
                            <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-900 dark:text-white">
                                <img :src="room.imageUrl"
                                     :alt="room.name"
                                     class="h-16 w-16 object-cover rounded">
                            </td>
                            <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-900 dark:text-white">{{ room.name
                                }}</td>

                            <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-900 dark:text-white">{{
                                room.pricePerNight }} บาท</td>

                            <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-900 dark:text-white">
                                {{ room.available ? 'เปิดขาย' : 'ปิดอยู่' }}
                            </td>
                            <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-900 dark:text-white">
                                <button type="button"
                                        class="inline-flex items-center px-3 py-2 text-sm font-medium text-center text-white bg-blue-600 rounded-lg focus:ring-4 focus:ring-blue-300 dark:focus:ring-blue-800 hover:bg-blue-700">
                                    แก้ไข
                                </button>
                            </td>
                        </tr>
                    </tbody>
                </table>
                <div class="mt-4">
                    <!-- <p class="text-lg font-semibold text-gray-900 dark:text-white">รวมยอดขาย: {{ totalSales }} บาท</p> -->
                </div>
            </div>
        </div>
    </section>
</template>

<script setup lang="ts">
import { ref, computed } from 'vue';

const rooms = ref([
    {
        id: 1,
        name: 'ทัวร์ญี่ปุ่น ช้อปปิ้ง ชิลล์ โตเกียว ชินจูกุ อาซากุสะ นาริตะ โอไดบะ (SL)',
        pricePerNight: 19888,

        capacity: '2 Adults',
        imageUrl: 'https://www.planetholidaystravel.com/wp-content/uploads/2025/04/banner-JSL221_310325-110800-1.jpg',
        available: true,
    },
    {
        id: 2,
        name: 'JAPAN ALPS SNOWWALL TOKYO OSAKA 6D 4N โดยสายการบินไทยแอร์เอเชีย เอ็กซ์ [XJ]',
        pricePerNight: 19999,

        capacity: '2 Adults',
        imageUrl: 'https://www.planetholidaystravel.com/wp-content/uploads/2025/01/Banner-12.png',
        available: false,
    },
    {
        id: 3,
        name: 'JAPAN ALPS SNOWWALL TOKYO OSAKA 6D 4N โดยสายการบินไทยแอร์เอเชีย เอ็กซ์ [XJ]',
        pricePerNight: 22999,

        capacity: '1 Adult',
        imageUrl: 'https://www.planetholidaystravel.com/wp-content/uploads/2025/03/BT-FUK04_VZ-1.jpg',
        available: true,
    },
    {
        id: 4,
        name: 'JAPAN ALPS SNOWWALL TOKYO OSAKA 6D 4N โดยสายการบินไทยแอร์เอเชีย เอ็กซ์ [XJ]',
        pricePerNight: 24996,

        capacity: '2 Adults',
        imageUrl: 'https://www.planetholidaystravel.com/wp-content/uploads/2025/03/BT-FUK03_VZ-1.jpg',
        available: false,
    },
]);

const totalSales = computed(() => {
    return rooms.value.reduce((sum, room) => sum + room.pricePerNight, 0);
});
</script>
