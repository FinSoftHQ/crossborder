<template>
    <UContainer>
        <section class="bg-gray-50 py-4 antialiased dark:bg-gray-900 md:py-6">
            <div class="max-w-screen-xl px-4 py-4 mx-auto sm:py-6 sm:px-6 lg:px-8">
                <!-- Search UI -->
                <div class="mb-8 flex flex-wrap items-center justify-center gap-6 bg-white p-6 rounded-lg shadow-md">
                    <div id="date-range-picker"
                         class="flex items-center">
                        <div class="relative">
                            <div class="absolute inset-y-0 start-0 flex items-center ps-3 pointer-events-none">
                                <svg class="w-4 h-4 text-gray-500 dark:text-gray-400"
                                     aria-hidden="true"
                                     xmlns="http://www.w3.org/2000/svg"
                                     fill="currentColor"
                                     viewBox="0 0 20 20">
                                    <path
                                          d="M20 4a2 2 0 0 0-2-2h-2V1a1 1 0 0 0-2 0v1h-3V1a1 1 0 0 0-2 0v1H6V1a1 1 0 0 0-2 0v1H2a2 2 0 0 0-2 2v2h20V4ZM0 18a2 2 0 0 0 2 2h16a2 2 0 0 0 2-2V8H0v10Zm5-8h10a1 1 0 0 1 0 2H5a1 1 0 0 1 0-2Z" />
                                </svg>
                            </div>
                            <input id="datepicker-range-start"
                                   name="start"
                                   type="date"
                                   v-model="searchCriteria.checkIn"
                                   class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full ps-10 p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
                                   placeholder="Select date start">
                        </div>
                        <span class="mx-4 text-gray-500">to</span>
                        <div class="relative">
                            <div class="absolute inset-y-0 start-0 flex items-center ps-3 pointer-events-none">
                                <svg class="w-4 h-4 text-gray-500 dark:text-gray-400"
                                     aria-hidden="true"
                                     xmlns="http://www.w3.org/2000/svg"
                                     fill="currentColor"
                                     viewBox="0 0 20 20">
                                    <path
                                          d="M20 4a2 2 0 0 0-2-2h-2V1a1 1 0 0 0-2 0v1h-3V1a1 1 0 0 0-2 0v1H6V1a1 1 0 0 0-2 0v1H2a2 2 0 0 0-2 2v2h20V4ZM0 18a2 2 0 0 0 2 2h16a2 2 0 0 0 2-2V8H0v10Zm5-8h10a1 1 0 0 1 0 2H5a1 1 0 0 1 0-2Z" />
                                </svg>
                            </div>
                            <input id="datepicker-range-end"
                                   name="end"
                                   type="date"
                                   v-model="searchCriteria.checkOut"
                                   class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full ps-10 p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
                                   placeholder="Select date end">
                        </div>
                    </div>
                    <div class="flex items-center">
                        <label for="guest-type"
                               class="mr-2 text-sm font-medium text-gray-900 dark:text-white">ประเภทผู้เข้าพัก</label>
                        <select id="guest-type"
                                v-model="searchCriteria.guestType"
                                class="block w-full rounded-lg border border-gray-300 bg-gray-50 p-2.5 text-sm text-gray-900 focus:border-blue-500 focus:ring-blue-500 dark:bg-gray-700 dark:border-gray-600 dark:text-white dark:focus:border-blue-500 dark:focus:ring-blue-500">
                            <option value="adult">ผู้ใหญ่</option>
                            <option value="child">เด็ก</option>
                        </select>
                    </div>
                    <UButton @click="searchRooms"
                             type="button"
                             class="inline-flex items-center rounded-lg bg-primary-700 px-5 py-2.5 text-sm font-medium text-white hover:bg-primary-800 focus:outline-none focus:ring-4 focus:ring-primary-300 dark:bg-primary-600 dark:hover:bg-primary-700 dark:focus:ring-primary-800">
                        ค้นหา
                    </UButton>
                </div>
                <!-- End Search UI -->
                <div class="mb-4 grid gap-4 sm:grid-cols-2 md:mb-8 lg:grid-cols-3 xl:grid-cols-4">
                    <div v-for="room in availableRooms"
                         :key="room.id"
                         class="rounded-lg border border-gray-200 bg-white p-6 shadow-sm dark:border-gray-700 dark:bg-gray-800">
                        <div class="h-56 w-full">
                            <a href="#">
                                <img :src="room.imageUrl"
                                     class="mx-auto h-full"
                                     :alt="room.name" />
                            </a>
                        </div>
                        <div class="pt-6">
                            <a href="#"
                               class="text-lg font-semibold leading-tight text-gray-900 hover:underline dark:text-white">
                                {{ room.hotelName }}
                            </a>
                            <p class="mt-2 text-sm text-gray-500 dark:text-gray-400">{{ room.type }} - {{ room.capacity
                                }}</p>
                            <div class="mt-2 flex items-center gap-2">
                                <div class="flex items-center">
                                    <svg v-for="n in Math.floor(room.rating)"
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
                                <p class="text-sm font-medium text-gray-900 dark:text-white">{{ room.rating }}</p>
                            </div>
                            <div class="mt-4 flex items-center justify-between gap-4">
                                <p class="text-2xl font-extrabold leading-tight text-gray-900 dark:text-white">฿ {{
                                    room.pricePerNight }}</p>
                                <UButton to="/NaLoeiWeb/orderSummary"
                                         class="inline-flex items-center rounded-lg bg-primary-700 px-5 py-2.5 text-sm font-medium text-white hover:bg-primary-800 focus:outline-none focus:ring-4 focus:ring-primary-300 dark:bg-primary-600 dark:hover:bg-primary-700 dark:focus:ring-primary-800">
                                    จองห้องพัก
                                </UButton>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>
    </UContainer>
</template>
<script setup lang="ts">
import { ref, computed } from 'vue';

const rooms = ref([
    {
        id: 1,
        name: '101',
        pricePerNight: 1500,
        type: 'Double Bed',
        capacity: '2 Adults',
        imageUrl: 'https://hotelsup.co/wp-content/uploads/2022/05/Double.png',
        available: true,
        hotelName: 'Hilton',
        rating: 4.5,
    },
    {
        id: 2,
        name: '102',
        pricePerNight: 3000,
        type: 'Queen Size Bed',
        capacity: '2 Adults',
        imageUrl: 'https://hotelsup.co/wp-content/uploads/2022/05/Queen-size.png',
        available: false,
        hotelName: 'Marriott',
        rating: 4.8,
    },
    {
        id: 3,
        name: '103',
        pricePerNight: 800,
        type: 'Single Bed',
        capacity: '1 Adult',
        imageUrl: 'https://hotelsup.co/wp-content/uploads/2022/05/Single.png',
        available: true,
        hotelName: 'Hilton',
        rating: 4.2,
    },
    {
        id: 4,
        name: '104',
        pricePerNight: 5000,
        type: 'Twin Bed',
        capacity: '2 Adults',
        imageUrl: 'https://hotelsup.co/wp-content/uploads/2022/05/Twin.png',
        available: false,
        hotelName: 'Marriott',
        rating: 4.9,
    },
    {
        id: 5,
        name: '105',
        pricePerNight: 1000,
        type: 'Double Bed',
        capacity: '2 Adults',
        imageUrl: 'https://hotelsup.co/wp-content/uploads/2022/05/Double.png',
        available: true,
        hotelName: 'Hilton',
        rating: 4.3,
    },
]);

const searchCriteria = ref({
    checkIn: '',
    checkOut: '',
    guestType: 'adult',
});

const availableRooms = computed(() => {
    // Filter rooms based on availability and search criteria
    return rooms.value.filter(room => {
        const isAvailable = room.available;
        const matchesGuestType = searchCriteria.value.guestType === 'adult' || room.capacity.includes('Adult');
        return isAvailable && matchesGuestType;
    });
});

function searchRooms() {
    console.log('Searching with criteria:', searchCriteria.value);
    // Add additional filtering logic if needed
}
</script>
