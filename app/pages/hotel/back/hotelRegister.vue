<template>
    <section class="bg-white py-8 antialiased dark:bg-gray-900 md:py-16">
        <div class="mx-auto max-w-3xl px-4 sm:px-6 lg:px-8">
            <div class="mx-auto max-w-3xl">
                <h2 class="text-xl font-semibold text-gray-900 dark:text-white sm:text-2xl">ลงทะเบียนโรงแรม</h2>
                <div class="mt-6 space-y-4 border-b border-t border-gray-200 py-8 dark:border-gray-700 sm:mt-8">
                    <h2 class="mb-4 text-xl font-bold text-gray-900 dark:text-white">กรอกข้อมูลโรงแรม</h2>
                    <form action="#">
                        <div class="grid gap-4 sm:grid-cols-2 sm:gap-6">
                            <!-- Hotel Name -->
                            <div class="sm:col-span-2">
                                <label for="hotel-name"
                                       class="block mb-2 text-sm font-medium text-gray-900 dark:text-white">ชื่อโรงแรม</label>
                                <input type="text"
                                       id="hotel-name"
                                       class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-primary-600 focus:border-primary-600 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-primary-500 dark:focus:border-primary-500"
                                       placeholder="กรอกชื่อโรงแรม"
                                       required>
                            </div>

                            <!-- Number of Buildings -->
                            <div class="sm:col-span-2">
                                <label for="building-count"
                                       class="block mb-2 text-sm font-medium text-gray-900 dark:text-white">จำนวนตึก</label>
                                <input type="number"
                                       id="building-count"
                                       class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-primary-600 focus:border-primary-600 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-primary-500 dark:focus:border-primary-500"
                                       placeholder="กรอกจำนวนตึก"
                                       required>
                            </div>

                            <!-- Building Details -->
                            <div class="sm:col-span-2">
                                <label for="building-details"
                                       class="block mb-2 text-sm font-medium text-gray-900 dark:text-white">รายละเอียดตึก</label>
                                <textarea id="building-details"
                                          class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-primary-600 focus:border-primary-600 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-primary-500 dark:focus:border-primary-500"
                                          placeholder="กรอกข้อมูล เช่น ตึก A มีกี่ชั้น แต่ละชั้นมีกี่ห้อง"
                                          rows="4"
                                          required></textarea>
                            </div>

                            <!-- Room Details -->
                            <div class="sm:col-span-2">
                                <label for="room-details"
                                       class="block mb-2 text-sm font-medium text-gray-900 dark:text-white">รายละเอียดห้อง</label>
                                <textarea id="room-details"
                                          class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-primary-600 focus:border-primary-600 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-primary-500 dark:focus:border-primary-500"
                                          placeholder="กรอกข้อมูล เช่น ห้อง 101 เตียงเดี่ยว ราคา 1000 บาท สถานะ: ว่าง"
                                          rows="6"
                                          required></textarea>
                            </div>
                        </div>
                        <button type="button"
                                class="inline-flex items-center px-5 py-2.5 mt-4 sm:mt-6 text-sm font-medium text-center text-white bg-primary-700 rounded-lg focus:ring-4 focus:ring-primary-200 dark:focus:ring-primary-900 hover:bg-primary-800">
                            บันทึกข้อมูล
                        </button>
                    </form>
                </div>
            </div>
        </div>
    </section>
</template>