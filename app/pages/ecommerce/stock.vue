<template>
    <section class="bg-white py-8 antialiased dark:bg-gray-900 md:py-16">
        <div class="mx-auto max-w-3xl">
            <div class="mx-auto max-w-3xl">
                <h2 class="text-xl font-semibold text-gray-900 dark:text-white sm:text-2xl">กรอกข้อมูลสินค้า</h2>
                <div class="mt-6 space-y-4 border-b border-t border-gray-200 py-8 dark:border-gray-700 sm:mt-8">
                    <h2 class="mb-4 text-xl font-bold text-gray-900 dark:text-white"></h2>
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
                                       class="block mb-2 text-sm font-medium text-gray-900 dark:text-white">จำนวนสินค้า
                                    (ก.ม)</label>
                                <input type="number"
                                       name="item-weight"
                                       id="item-weight"
                                       class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-primary-600 focus:border-primary-600 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-primary-500 dark:focus:border-primary-500"
                                       placeholder="กรอกจำนวนสินค้า"
                                       required="">
                            </div>
                        </div>
                        <button type="submit"
                                class="inline-flex items-center px-5 py-2.5 mt-4 sm:mt-6 text-sm font-medium text-center text-white bg-primary-700 rounded-lg focus:ring-4 focus:ring-primary-200 dark:focus:ring-primary-900 hover:bg-primary-800">
                            บันทึกข้อมูล
                        </button>
                    </form>
                </div>
            </div>
        </div>
    </section>
</template>