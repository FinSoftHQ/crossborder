<template>
    <UContainer>
        <section class="bg-gray-50 py-4 antialiased dark:bg-gray-900 md:py-6">
            <div class="max-w-screen-xl px-4 py-4 mx-auto sm:py-6 sm:px-6 lg:px-8">
                
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
