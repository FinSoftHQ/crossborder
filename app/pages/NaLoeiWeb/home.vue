<template>
    <UContainer>
        <section class="bg-gray-50 py-8 antialiased dark:bg-gray-900 md:py-12">
            <div class="mx-auto max-w-screen-xl px-4 2xl:px-0">
                <!-- Heading -->
                <div class="mb-8 text-center">
                    <h2 class="mb-4 text-3xl font-extrabold text-gray-900 dark:text-white sm:text-4xl">
                        ที่พัก รถเช่า และทัวร์แนะนำสำหรับคุณ
                    </h2>
                    <div class="bg-white p-6 rounded-lg shadow-md">
                    <div class="flex justify-center mb-4">
                        <div class="relative w-full max-w-lg">
                            <input 
                                v-model="searchQuery" 
                                type="text" 
                                placeholder="ค้นหาโรงแรม ทัวร์ หรือบริษัท..." 
                                class="w-full p-2 pl-10 border border-gray-300 rounded-lg focus:ring-blue-500 focus:border-blue-500 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
                            />
                            <div class="absolute inset-y-0 left-0 flex items-center pl-3 pointer-events-none">
                                <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-gray-500 dark:text-gray-400" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 6a4 4 0 100 8 4 4 0 000-8zm8 14l-4-4" />
                                </svg>
                            </div>
                        </div>
                    </div>
                        <!-- Search UI -->
                        <div class="flex flex-wrap items-center justify-center gap-6">
                            <div id="date-range-picker" class="flex items-center">
                                <div class="relative">
                                    <label for="datepicker-range-start" class="sr-only">Check-in Date</label>
                                    <div class="absolute inset-y-0 left-0 flex items-center pl-3 pointer-events-none">
                                        <svg class="w-5 h-5 text-gray-500" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="currentColor" viewBox="0 0 20 20">
                                            <path d="M20 4a2 2 0 0 0-2-2h-2V1a1 1 0 0 0-2 0v1h-3V1a1 1 0 0 0-2 0v1H6V1a1 1 0 0 0-2 0v1H2a2 2 0 0 0-2 2v2h20V4ZM0 18a2 2 0 0 0 2 2h16a2 2 0 0 0 2-2V8H0v10Zm5-8h10a1 1 0 0 1 0 2H5a1 1 0 0 1 0-2Z" />
                                        </svg>
                                    </div>
                                    <input id="datepicker-range-start" name="start" type="date" v-model="searchCriteria.checkIn" class="block w-full pl-10 p-2.5 text-sm text-gray-900 border border-gray-300 rounded-lg bg-gray-50 focus:ring-blue-500 focus:border-blue-500" placeholder="Check-in">
                                </div>
                                <span class="mx-4 text-gray-500">to</span>
                                <div class="relative">
                                    <label for="datepicker-range-end" class="sr-only">Check-out Date</label>
                                    <div class="absolute inset-y-0 left-0 flex items-center pl-3 pointer-events-none">
                                        <svg class="w-5 h-5 text-gray-500" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="currentColor" viewBox="0 0 20 20">
                                            <path d="M20 4a2 2 0 0 0-2-2h-2V1a1 1 0 0 0-2 0v1h-3V1a1 1 0 0 0-2 0v1H6V1a1 1 0 0 0-2 0v1H2a2 2 0 0 0-2 2v2h20V4ZM0 18a2 2 0 0 0 2 2h16a2 2 0 0 0 2-2V8H0v10Zm5-8h10a1 1 0 0 1 0 2H5a1 1 0 0 1 0-2Z" />
                                        </svg>
                                    </div>
                                    <input id="datepicker-range-end" name="end" type="date" v-model="searchCriteria.checkOut" class="block w-full pl-10 p-2.5 text-sm text-gray-900 border border-gray-300 rounded-lg bg-gray-50 focus:ring-blue-500 focus:border-blue-500" placeholder="Check-out">
                                </div>
                            </div>
                            <div class="flex items-center">
                                <label for="guest-type" class="mr-2 text-sm font-medium text-gray-900">ประเภทผู้เข้าพัก</label>
                                <select id="guest-type" v-model="searchCriteria.guestType" class="block w-full rounded-lg border border-gray-300 bg-gray-50 p-2.5 text-sm text-gray-900 focus:border-blue-500 focus:ring-blue-500">
                                    <option value="adult">ผู้ใหญ่</option>
                                    <option value="child">เด็ก</option>
                                </select>
                            </div>
                            <UButton @click="searchRooms" type="button" class="inline-flex items-center rounded-lg bg-blue-600 px-5 py-2.5 text-sm font-medium text-white hover:bg-blue-700 focus:outline-none focus:ring-4 focus:ring-blue-300">
                                ค้นหา
                            </UButton>
                        </div>
                    </div>
                </div>
                <div class="mt-8 mb-8 flex justify-between items-center">
                    <h2 class="text-md font-bold text-gray-900 dark:text-white sm:text-2xl">
                        ที่พักแนะนำสำหรับท่านโดยเฉพาะ
                    </h2>
                    <a href="/NaLoeiWeb/hotelBooking"
                       class="text-blue-600 hover:underline dark:text-blue-400">
                        ดูที่พักเพิ่มเติม >>
                    </a>
                </div>
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
                <div class="mt-8 mb-8 flex justify-between items-center">
                    <h2 class="text-md font-bold text-gray-900 dark:text-white sm:text-2xl">
                        รถเช่าที่แนะนำสำหรับท่านโดยเฉพาะ
                    </h2>
                    <a href="/NaLoeiWeb/carBooking"
                       class="text-blue-600 hover:underline dark:text-blue-400">
                        ดูรถเช่าเพิ่มเติม >>
                    </a>
                </div>
                <div class="mb-4 grid gap-4 sm:grid-cols-2 md:mb-8 lg:grid-cols-3 xl:grid-cols-4">
                    <div v-for="car in cars"
                         :key="car.id"
                         class="rounded-lg border border-gray-200 bg-white p-6 shadow-sm dark:border-gray-700 dark:bg-gray-800">
                        <div class="h-56 w-full">
                            <a href="#">
                                <img :src="car.imageUrl"
                                     class="mx-auto h-full dark:hidden"
                                     :alt="car.name" />
                                <img :src="car.darkImageUrl"
                                     class="mx-auto hidden h-full dark:block"
                                     :alt="car.name" />
                            </a>
                        </div>
                        <div class="pt-6">
                            <a href="#"
                               class="text-lg font-semibold leading-tight text-gray-900 hover:underline dark:text-white">{{
                                car.name }}</a>
                            <div class="mt-2 flex items-center gap-2">
                                <p class="text-sm font-medium text-gray-900 dark:text-white">{{ car.seats }}</p>
                                <p class="text-sm font-medium text-gray-500 dark:text-gray-400">({{ car.type }})</p>
                            </div>
                        </div>
                        <div class="mt-4 flex items-center justify-between gap-4">
                            <p class="text-2xl font-extrabold leading-tight text-gray-900 dark:text-white">฿ {{
                                car.pricePerDay }}</p>
                            <UButton
                                     class="inline-flex items-center rounded-lg bg-primary-700 px-5 py-2.5 text-sm font-medium text-white hover:bg-primary-800 focus:outline-none focus:ring-4 focus:ring-primary-300 dark:bg-primary-600 dark:hover:bg-primary-700 dark:focus:ring-primary-800">
                                จองรถ
                            </UButton>
                        </div>
                    </div>
                </div>
                <div class="mt-8 mb-8 flex justify-between items-center">
                    <h2 class="text-md font-bold text-gray-900 dark:text-white sm:text-2xl">
                        ทัวร์แนะนำสำหรับท่านโดยเฉพาะ
                    </h2>
                    <a href="/packageTour/home"
                       class="text-blue-600 hover:underline dark:text-blue-400">
                        ดูทัวร์เพิ่มเติม >>
                    </a>
                </div>
                <div class="mb-4 grid gap-4 sm:grid-cols-2 md:mb-8 lg:grid-cols-3 xl:grid-cols-4">
                    <div v-for="tour in tours"
                         :key="tour.id"
                         class="rounded-lg border border-gray-200 bg-white p-4 shadow-sm dark:border-gray-700 dark:bg-gray-800">
                        <div class="mb-2 flex items-center justify-center rounded-lg">
                            <div class="flex items-center justify-center">
                                <p class="text-sm font-bold text-gray-700 dark:text-white">{{ tour.date }}</p>
                            </div>
                        </div>
                        <div class="h-56 w-full">
                            <a href="#">
                                <img class="mx-auto h-full dark:hidden"
                                     :src="tour.image"
                                     alt="" />
                                <img class="mx-auto hidden h-full dark:block"
                                     src="https://flowbite.s3.amazonaws.com/blocks/e-commerce/imac-front-dark.svg"
                                     alt="" />
                            </a>
                        </div>
                        <div class="pt-6">
                            <a href="#"
                               class="text-md font-semibold leading-tight text-gray-900 hover:underline dark:text-white">{{
                                tour.title }}</a>
                            <div class="mt-8 flex items-center gap-2">
                                <div class="flex items-center">
                                    <UIcon name="i-heroicons-calendar-days"
                                           class="mr-2" />
                                    <p class="text-sm font-bold text-gray-500 dark:text-white">{{ tour.duration }}</p>
                                </div>
                            </div>
                            <div class="mt-2 flex items-center gap-2">
                                <div class="flex items-center">
                                    <UIcon name="i-ion:bed-outline"
                                           class="mr-2" />
                                    <p class="text-sm font-bold text-gray-500 dark:text-white mr-2">โรงแรม</p>
                                    <svg v-for="star in 5"
                                         :key="star"
                                         class="h-4 w-4 text-yellow-400"
                                         xmlns="http://www.w3.org/2000/svg"
                                         fill="currentColor"
                                         viewBox="0 0 24 24">
                                        <path
                                              d="M13.8 4.2a2 2 0 0 0-3.6 0L8.4 8.4l-4.6.3a2 2 0 0 0-1.1 3.5l3.5 3-1 4.4c-.5 1.7 1.4 3 2.9 2.1l3.9-2.3 3.9 2.3c1.5 1 3.4-.4 3-2.1l-1-4.4 3.4-3a2 2 0 0 0-1.1-3.5l-4.6-.3-1.8-4.2Z" />
                                    </svg>
                                </div>
                            </div>
                            <div class="mt-2 flex items-center gap-2">
                                <div class="flex items-center">
                                    <UIcon name="i-clarity:plane-line"
                                           class="mr-2" />
                                    <img :src="tour.airlineLogo"
                                         alt="Airline Logo"
                                         class="h-5" />
                                </div>
                            </div>
                            <p class="text-xs font-extrabold leading-tight text-gray-500 dark:text-white mt-3">
                                ราคาเริ่มต้น บาท/ท่าน</p>
                            <div class="flex items-center justify-between gap-4">
                                <p class="text-2xl font-extrabold leading-tight text-red-700 dark:text-white">{{
                                    tour.price }}</p>
                                <NuxtLink :to="tour.link"
                                          class="inline-flex items-center rounded-lg bg-primary-700 px-5 py-2.5 text-sm font-medium text-white hover:bg-primary-800 focus:outline-none focus:ring-4 focus:ring-primary-300 dark:bg-primary-600 dark:hover:bg-primary-700 dark:focus:ring-primary-800">
                                    ดูรายละเอียด
                                </NuxtLink>
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

// Define product categories
const categories = ref([
    {
        id: 1,
        name: 'ห้องพัก',
        iconUrl: 'i-mdi-hotel',
        link: '/NaLoeiWeb/hotelBooking',
    },
    {
        id: 2,
        name: 'จองรถ',
        iconUrl: 'i-mdi-car',
        link: '/NaLoeiWeb/carBooking',
    },
    {
        id: 3,
        name: 'จองทัวร์',
        iconUrl: 'i-mdi-map',
        link: '/packageTour/home',
    },
]);

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
    {
        id: 6,
        name: '106',
        pricePerNight: 2000,
        type: 'King Size Bed',
        capacity: '2 Adults',
        imageUrl: 'https://hotelsup.co/wp-content/uploads/2022/05/King-size.png',
        available: true,
        hotelName: 'Sheraton',
        rating: 4.7,
    },
]);

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
    },
    {
        id: 2,
        name: 'Platinum Double Decker',
        pricePerDay: 14000,
        type: 'Luxury Coach',
        seats: '55 Seats',
        imageUrl: 'https://www.thanatwit.com/wp-content/uploads/2022/07/bus-3-2.jpg',
        darkImageUrl: 'https://www.thanatwit.com/wp-content/uploads/2022/07/bus-3-2.jpg',
        luxury: true,
        registrationNumber: 'LUX-3456',
    },
    {
        id: 3,
        name: 'Euro 13.8 Single Decker',
        pricePerDay: 13000,
        type: 'Imported Coach',
        seats: '50 Seats',
        imageUrl: 'https://www.thanatwit.com/wp-content/uploads/2022/07/bus-4-2.jpg',
        darkImageUrl: 'https://www.thanatwit.com/wp-content/uploads/2022/07/bus-4-2.jpg',
        popular: true,
        registrationNumber: 'EURO-7890',
    },
    {
        id: 4,
        name: 'Premium Van',
        pricePerDay: 4500,
        type: 'Van',
        seats: '10 Seats',
        imageUrl: 'https://www.thanatwit.com/wp-content/uploads/2022/07/van-5-1.jpg',
        darkImageUrl: 'https://www.thanatwit.com/wp-content/uploads/2022/07/van-5-1.jpg',
        fastBooking: true,
        registrationNumber: 'VAN-1122',
    },
]);

const tours = ref([
    {
        id: 1,
        date: 'พ.ค. 68 - มิ.ย. 68',
        image: 'https://www.planetholidaystravel.com/wp-content/uploads/2025/04/banner-JSL221_310325-110800-1.jpg',
        title: 'ทัวร์ญี่ปุ่น ช้อปปิ้ง ชิลล์ โตเกียว ชินจูกุ อาซากุสะ นาริตะ โอไดบะ (SL)',
        duration: '4 วัน 3 คืน',
        airlineLogo: 'https://logos-download.com/wp-content/uploads/2016/05/Lion_Air_logo_logotype.png',
        price: '19,888',
        link: '/packageTour/detail',
    },
    {
        id: 2,
        date: '22 - 26 ม.ค. 68',
        image: 'https://www.planetholidaystravel.com/wp-content/uploads/2025/01/Banner-12.png',
        title: 'JAPAN ALPS SNOWWALL TOKYO OSAKA 6D 4N โดยสายการบินไทยแอร์เอเชีย เอ็กซ์ [XJ]',
        duration: '5 วัน 3 คืน',
        airlineLogo: 'https://logos-download.com/wp-content/uploads/2016/05/Lion_Air_logo_logotype.png',
        price: '19,999',
        link: '/packageTour/detail',
    },
    {
        id: 3,
        date: 'พ.ค. 68 - ก.ย. 68',
        image: 'https://www.planetholidaystravel.com/wp-content/uploads/2025/03/BT-FUK04_VZ-1.jpg',
        title: 'JAPAN ALPS SNOWWALL TOKYO OSAKA 6D 4N โดยสายการบินไทยแอร์เอเชีย เอ็กซ์ [XJ]',
        duration: '5 วัน 3 คืน',
        airlineLogo: 'https://logos-download.com/wp-content/uploads/2016/05/Lion_Air_logo_logotype.png',
        price: '22,999',
        link: '/packageTour/detail',
    },
    {
        id: 4,
        date: 'พ.ค. 68 - ก.ย. 68',
        image: 'https://www.planetholidaystravel.com/wp-content/uploads/2025/03/BT-FUK03_VZ-1.jpg',
        title: 'JAPAN ALPS SNOWWALL TOKYO OSAKA 6D 4N โดยสายการบินไทยแอร์เอเชีย เอ็กซ์ [XJ]',
        duration: '4 วัน 3 คืน',
        airlineLogo: 'https://logos-download.com/wp-content/uploads/2016/05/Lion_Air_logo_logotype.png',
        price: '24,996',
        link: '/packageTour/detail',
    },
]);

const availableRooms = computed(() => {
    return rooms.value.filter(room => room.available);
});

const searchCriteria = ref({
    checkIn: '',
    checkOut: '',
    guestType: 'adult',
});



function searchRooms() {
    console.log('Searching with criteria:', searchCriteria.value);
    // Add additional filtering logic if needed
}
</script>
