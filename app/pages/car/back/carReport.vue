<template>
    <section class="bg-white py-8 antialiased dark:bg-gray-900 md:py-16">
        <div class="mx-auto max-w-5xl px-4 sm:px-6 lg:px-8">
            <h2 class="text-xl font-semibold text-gray-900 dark:text-white sm:text-2xl">รายงานสรุปการเช่ารถ</h2>
            <div class="mt-6 space-y-4 border-b border-t border-gray-200 py-8 dark:border-gray-700 sm:mt-8">
                <div class="flex justify-between items-center">
                    <h3 class="mb-4 text-lg font-bold text-gray-900 dark:text-white">ข้อมูลการเช่าวันนี้</h3>
                    <NuxtLink to="/car/back/carRegister">
                        <button type="button"
                                class="inline-flex items-center px-5 py-2.5 mt-4 sm:mt-6 text-sm font-medium text-center text-white bg-primary-700 rounded-lg focus:ring-4 focus:ring-primary-200 dark:focus:ring-primary-900 hover:bg-primary-800">
                            เพิ่มรถให้เช่า
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
                                ชื่อรถ</th>
                            <th scope="col"
                                class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider dark:text-gray-400">
                                ประเภทรถ</th>
                            <th scope="col"
                                class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider dark:text-gray-400">
                                ราคา/วัน</th>
                            <th scope="col"
                                class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider dark:text-gray-400">
                                จำนวนที่นั่ง</th>
                            <th scope="col"
                                class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider dark:text-gray-400">
                                สถานะ</th>
                        </tr>
                    </thead>
                    <tbody class="bg-white divide-y divide-gray-200 dark:bg-gray-700 dark:divide-gray-600">
                        <tr v-for="car in cars"
                            :key="car.id">
                            <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-900 dark:text-white">
                                <img :src="car.imageUrl"
                                     :alt="car.name"
                                     class="h-16 w-16 object-cover rounded">
                            </td>
                            <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-900 dark:text-white">{{ car.name }}
                            </td>
                            <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-900 dark:text-white">{{ car.type }}
                            </td>
                            <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-900 dark:text-white">{{
                                car.pricePerDay }} บาท</td>
                            <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-900 dark:text-white">{{ car.seats
                            }}</td>
                            <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-900 dark:text-white">
                                {{ car.isAvailable ? 'ว่าง' : 'จองแล้ว' }}
                            </td>
                        </tr>
                    </tbody>
                </table>
                <div class="mt-4">
                    <p class="text-lg font-semibold text-gray-900 dark:text-white">รวมยอดเช่า: {{ totalRental }} บาท</p>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup lang="ts">
import { ref, computed } from 'vue';

const cars = ref([
    {
        id: 1,
        name: 'Zhong Tong Single Decker',
        pricePerDay: 7000,
        type: 'Bus',
        seats: '40 Seats',
        imageUrl: 'https://www.thanatwit.com/wp-content/uploads/2022/07/bus-5-1.jpg',
        darkImageUrl: 'https://www.thanatwit.com/wp-content/uploads/2022/07/bus-5-1.jpg',
        bestSeller: true,
        registrationNumber: 'BUS-1234',
        isAvailable: true,
    },
    {
        id: 2,
        name: 'Single Decker Coach',
        pricePerDay: 9000,
        type: 'Coach',
        seats: '45 Seats',
        imageUrl: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQfJjNpoeGZt17DvcNROPl0mig6JvCC_OEYhQ&s',
        darkImageUrl: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQfJjNpoeGZt17DvcNROPl0mig6JvCC_OEYhQ&s',
        fastBooking: true,
        registrationNumber: 'COACH-5678',
        isAvailable: false,
    },
    {
        id: 3,
        name: 'Standard Double Decker',
        pricePerDay: 11000,
        type: 'Tour Bus',
        seats: '50 Seats',
        imageUrl: 'https://image.travelcatteralls.co.uk/images/tbs/Image%20Grid/img_8301.jpeg',
        darkImageUrl: 'https://image.travelcatteralls.co.uk/images/tbs/Image%20Grid/img_8301.jpeg',
        bestPrice: true,
        registrationNumber: 'TOUR-9012',
        isAvailable: true,
    },
    {
        id: 4,
        name: 'Platinum Double Decker',
        pricePerDay: 14000,
        type: 'Luxury Coach',
        seats: '55 Seats',
        imageUrl: 'https://www.thanatwit.com/wp-content/uploads/2022/07/bus-3-2.jpg',
        darkImageUrl: 'https://www.thanatwit.com/wp-content/uploads/2022/07/bus-3-2.jpg',
        luxury: true,
        registrationNumber: 'LUX-3456',
        isAvailable: false,
    },
    {
        id: 5,
        name: 'Euro 13.8 Single Decker',
        pricePerDay: 13000,
        type: 'Imported Coach',
        seats: '50 Seats',
        imageUrl: 'https://www.thanatwit.com/wp-content/uploads/2022/07/bus-4-2.jpg',
        darkImageUrl: 'https://www.thanatwit.com/wp-content/uploads/2022/07/bus-4-2.jpg',
        popular: true,
        registrationNumber: 'EURO-7890',
        isAvailable: true,
    },
    {
        id: 6,
        name: 'Premium Van',
        pricePerDay: 4500,
        type: 'Van',
        seats: '10 Seats',
        imageUrl: 'https://www.thanatwit.com/wp-content/uploads/2022/07/van-5-1.jpg',
        darkImageUrl: 'https://www.thanatwit.com/wp-content/uploads/2022/07/van-5-1.jpg',
        fastBooking: true,
        registrationNumber: 'VAN-1122',
        isAvailable: false,
    },
]);

const totalRental = computed(() => {
    return cars.value.reduce((sum, car) => sum + car.pricePerDay, 0);
});
</script>
