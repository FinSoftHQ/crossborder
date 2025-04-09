<template>
    <section class="bg-white py-8 antialiased dark:bg-gray-900 md:py-16">
        <div class="mx-auto max-w-3xl px-4 sm:px-6 lg:px-8">
            <div class="mx-auto max-w-3xl">
                <h2 class="text-xl font-semibold text-gray-900 dark:text-white sm:text-2xl">ลงทะเบียนรถ</h2>
                <div class="mt-6 space-y-4 border-b border-t border-gray-200 py-8 dark:border-gray-700 sm:mt-8">
                    <h2 class="mb-4 text-xl font-bold text-gray-900 dark:text-white">กรอกข้อมูลรถ</h2>
                    <form action="#">
                        <div class="grid gap-4 sm:grid-cols-2 sm:gap-6">
                            <!-- Car Name -->
                            <div class="sm:col-span-2">
                                <label for="car-name"
                                       class="block mb-2 text-sm font-medium text-gray-900 dark:text-white">ชื่อรถ</label>
                                <input type="text"
                                       id="car-name"
                                       class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-primary-600 focus:border-primary-600 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-primary-500 dark:focus:border-primary-500"
                                       placeholder="กรอกชื่อรถ เช่น Zhong Tong Single Decker"
                                       required>
                            </div>

                            <!-- Car Image -->
                            <div class="sm:col-span-2">
                                <label for="car-image"
                                       class="block mb-2 text-sm font-medium text-gray-900 dark:text-white">เพิ่มรูปภาพรถ</label>
                                <div class="flex items-start justify-start sm:justify-start w-full">
                                    <label for="car-image"
                                           class="flex flex-col items-center justify-center w-full max-w-xs h-[250px] border-2 border-gray-300 border-dashed rounded-lg cursor-pointer bg-gray-50 dark:hover:bg-bray-800 dark:bg-gray-700 hover:bg-gray-100 dark:border-gray-600 dark:hover:border-gray-500 dark:hover:bg-gray-600">
                                        <div class="flex flex-col items-center justify-center pt-5 pb-6">
                                            <svg aria-hidden="true"
                                                 class="w-10 h-10 mb-3 text-gray-400"
                                                 fill="none"
                                                 stroke="currentColor"
                                                 viewBox="0 0 24 24"
                                                 xmlns="http://www.w3.org/2000/svg">
                                                <path stroke-linecap="round"
                                                      stroke-linejoin="round"
                                                      stroke-width="2"
                                                      d="M12 16v-4m0 0V8m0 4h4m-4 0H8m12 4v4H4v-4m16 0l-4-4m0 0l-4 4m4-4H8">
                                                </path>
                                            </svg>
                                            <p class="mb-2 text-sm text-gray-500 dark:text-gray-400"><span
                                                      class="font-semibold">คลิกเพื่ออัปโหลด</span>
                                            </p>
                                            <p class="text-xs text-gray-500 dark:text-gray-400">PNG, JPG (สูงสุด 2MB)
                                            </p>
                                        </div>
                                        <input id="car-image"
                                               type="file"
                                               class="hidden"
                                               accept="image/*" />
                                    </label>
                                </div>
                            </div>

                            <!-- Car Type -->
                            <div class="sm:col-span-2">
                                <label for="car-type"
                                       class="block mb-2 text-sm font-medium text-gray-900 dark:text-white">ประเภทรถ</label>
                                <select id="car-type"
                                        class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-primary-600 focus:border-primary-600 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-primary-500 dark:focus:border-primary-500"
                                        required>
                                    <option value="Bus">Bus</option>
                                    <option value="Coach">Coach</option>
                                    <option value="Tour Bus">Tour Bus</option>
                                    <option value="Luxury Coach">Luxury Coach</option>
                                    <option value="Van">Van</option>
                                </select>
                            </div>

                            <!-- Car Price -->
                            <div class="sm:col-span-2">
                                <label for="car-price"
                                       class="block mb-2 text-sm font-medium text-gray-900 dark:text-white">ราคาต่อวัน</label>
                                <input type="number"
                                       id="car-price"
                                       class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-primary-600 focus:border-primary-600 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-primary-500 dark:focus:border-primary-500"
                                       placeholder="กรอกราคาต่อวัน เช่น 7000"
                                       required>
                            </div>

                            <!-- Car Seats -->
                            <div class="sm:col-span-2">
                                <label for="car-seats"
                                       class="block mb-2 text-sm font-medium text-gray-900 dark:text-white">จำนวนที่นั่ง</label>
                                <input type="text"
                                       id="car-seats"
                                       class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-primary-600 focus:border-primary-600 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-primary-500 dark:focus:border-primary-500"
                                       placeholder="กรอกจำนวนที่นั่ง เช่น 40 Seats"
                                       required>
                            </div>

                            <!-- Car Availability -->
                            <div class="sm:col-span-2">
                                <label for="car-available"
                                       class="block mb-2 text-sm font-medium text-gray-900 dark:text-white">สถานะรถ</label>
                                <select id="car-available"
                                        class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-primary-600 focus:border-primary-600 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-primary-500 dark:focus:border-primary-500"
                                        required>
                                    <option value="true">ว่าง</option>
                                    <option value="false">จองแล้ว</option>
                                </select>
                            </div>
                        </div>
                        <NuxtLink to="/car/back/carReport">
                            <button type="button"
                                    class="inline-flex items-center px-5 py-2.5 mt-4 sm:mt-6 text-sm font-medium text-center text-white bg-primary-700 rounded-lg focus:ring-4 focus:ring-primary-200 dark:focus:ring-primary-900 hover:bg-primary-800">
                                บันทึกข้อมูล
                            </button>
                        </NuxtLink>
                    </form>
                </div>
            </div>
        </div>
    </section>
</template>