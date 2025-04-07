<template>
    <section class="bg-white py-8 antialiased dark:bg-gray-900 md:py-16">
        <div class="mx-auto max-w-3xl px-4 sm:px-6 lg:px-8">
            <div class="mx-auto max-w-3xl">
                <h2 class="text-xl font-semibold text-gray-900 dark:text-white sm:text-2xl">ลงขายสินค้า</h2>
                <div class="mt-6 space-y-4 border-b border-t border-gray-200 py-8 dark:border-gray-700 sm:mt-8">
                    <h2 class="mb-4 text-xl font-bold text-gray-900 dark:text-white">กรอกข้อมูลสินค้า</h2>
                    <form action="#">
                        <div class="grid gap-4 sm:grid-cols-2 sm:gap-6">
                            <!-- Store/Farm/Location Name -->
                            <div class="sm:col-span-2">
                                <label for="location"
                                       class="block mb-2 text-sm font-medium text-gray-900 dark:text-white">ชื่อร้านค้า/สวน/สถานที่</label>
                                <select id="location"
                                        class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-primary-500 focus:border-primary-500 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-primary-500 dark:focus:border-primary-500">
                                    <option selected="">เลือกชื่อร้านค้า/สวน/สถานที่</option>
                                    <option value="สวนผลไม้สุขใจ">สวนผลไม้สุขใจ</option>
                                    <option value="ฟาร์มผักสด">ฟาร์มผักสด</option>
                                    <option value="ร้านสมุนไพรไทย">ร้านสมุนไพรไทย</option>
                                    <option value="สวนเกษตรอินทรีย์">สวนเกษตรอินทรีย์</option>
                                    <option value="ฟาร์มออร์แกนิค">ฟาร์มออร์แกนิค</option>
                                    <option value="ร้านผลิตภัณฑ์ธรรมชาติ">ร้านผลิตภัณฑ์ธรรมชาติ</option>
                                    <option value="สวนสมุนไพรสุขภาพ">สวนสมุนไพรสุขภาพ</option>
                                </select>
                            </div>

                            <!-- Product Image -->
                            <div class="sm:col-span-2">
                                <label for="product-image"
                                       class="block mb-2 text-sm font-medium text-gray-900 dark:text-white">เพิ่มรูปสินค้า</label>
                                <div class="flex items-start justify-start sm:justify-start w-full">
                                    <label for="product-image"
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
                                                      d="M12 16v-4m0 0V8m0 4h4m-4 0H8m12 4v4H4v-4m16 0l-4-4m0 0l-4 4m4-4H8"></path>
                                            </svg>
                                            <p class="mb-2 text-sm text-gray-500 dark:text-gray-400"><span
                                                      class="font-semibold">คลิกเพื่ออัปโหลด</span>
                                            </p>
                                            <p class="text-xs text-gray-500 dark:text-gray-400">PNG, JPG (สูงสุด 2MB)
                                            </p>
                                        </div>
                                        <input id="product-image"
                                               type="file"
                                               class="hidden"
                                               accept="image/*" />
                                    </label>
                                </div>
                            </div>

                            <!-- Product Name -->
                            <div class="sm:col-span-2">
                                <label for="product-name"
                                       class="block mb-2 text-sm font-medium text-gray-900 dark:text-white">ชื่อสินค้า</label>
                                <input type="text"
                                       name="product-name"
                                       id="product-name"
                                       class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-primary-600 focus:border-primary-600 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-primary-500 dark:focus:border-primary-500"
                                       placeholder="กรอกชื่อสินค้า"
                                       required="">
                            </div>

                            <!-- Product Type -->
                            <div class="sm:col-span-2">
                                <label for="category"
                                       class="block mb-2 text-sm font-medium text-gray-900 dark:text-white">ประเภทสินค้า</label>
                                <select id="category"
                                        class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-primary-500 focus:border-primary-500 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-primary-500 dark:focus:border-primary-500">
                                    <option selected="">เลือกประเภทสินค้า</option>
                                    <option value="สด / แห้ง">สด / แห้ง</option>
                                    <option value="ผง">ผง</option>
                                    <option value="สารสกัด">สารสกัด</option>
                                    <option value="ผลิตภัณฑ์ green product (ของกิน ของใช้)">ผลิตภัณฑ์ green product
                                        (ของกิน
                                        ของใช้)</option>
                                    <option value="อาหารเสริม">อาหารเสริม</option>
                                </select>
                            </div>
                            <!-- Quantity -->
                            <div class="sm:col-span-2">
                                <label for="item-weight"
                                       class="block mb-2 text-sm font-medium text-gray-900 dark:text-white">จำนวนสินค้า</label>
                                <div class="flex flex-col gap-4">
                                    <input type="number"
                                           name="item-weight"
                                           id="item-weight"
                                           class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-primary-600 focus:border-primary-600 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-primary-500 dark:focus:border-primary-500"
                                           placeholder="กรอกจำนวนสินค้า"
                                           required="">
                                    <h3 class="mb-4 font-semibold text-gray-900 dark:text-white">หน่วยสินค้า</h3>
                                    <ul
                                        class="items-center w-full text-sm font-medium text-gray-900 bg-white border border-gray-200 rounded-lg sm:flex dark:bg-gray-700 dark:border-gray-600 dark:text-white">
                                        <li
                                            class="w-full border-b border-gray-200 sm:border-b-0 sm:border-r dark:border-gray-600">
                                            <div class="flex items-center ps-3">
                                                <input id="unit-piece"
                                                       type="radio"
                                                       value="ชิ้น"
                                                       name="item-unit"
                                                       class="w-4 h-4 text-blue-600 bg-gray-100 border-gray-300 focus:ring-blue-500 dark:focus:ring-blue-600 dark:ring-offset-gray-700 dark:focus:ring-offset-gray-700 focus:ring-2 dark:bg-gray-600 dark:border-gray-500">
                                                <label for="unit-piece"
                                                       class="w-full py-3 ms-2 text-sm font-medium text-gray-900 dark:text-gray-300">ชิ้น/อัน</label>
                                            </div>
                                        </li>
                                        <li
                                            class="w-full border-b border-gray-200 sm:border-b-0 sm:border-r dark:border-gray-600">
                                            <div class="flex items-center ps-3">
                                                <input id="unit-kg"
                                                       type="radio"
                                                       value="กิโลกรัม"
                                                       name="item-unit"
                                                       class="w-4 h-4 text-blue-600 bg-gray-100 border-gray-300 focus:ring-blue-500 dark:focus:ring-blue-600 dark:ring-offset-gray-700 dark:focus:ring-offset-gray-700 focus:ring-2 dark:bg-gray-600 dark:border-gray-500">
                                                <label for="unit-kg"
                                                       class="w-full py-3 ms-2 text-sm font-medium text-gray-900 dark:text-gray-300">กิโลกรัม</label>
                                            </div>
                                        </li>
                                        <li class="w-full dark:border-gray-600">
                                            <div class="flex items-center ps-3">
                                                <input id="unit-count"
                                                       type="radio"
                                                       value="จำนวน"
                                                       name="item-unit"
                                                       class="w-4 h-4 text-blue-600 bg-gray-100 border-gray-300 focus:ring-blue-500 dark:focus:ring-blue-600 dark:ring-offset-gray-700 dark:focus:ring-offset-gray-700 focus:ring-2 dark:bg-gray-600 dark:border-gray-500">
                                                <label for="unit-count"
                                                       class="w-full py-3 ms-2 text-sm font-medium text-gray-900 dark:text-gray-300">จำนวน</label>
                                            </div>
                                        </li>
                                    </ul>
                                </div>
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