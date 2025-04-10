<template>
  <section class="bg-white py-8 antialiased dark:bg-gray-900 md:py-16">
      <div class="mx-auto max-w-3xl px-4 sm:px-6 lg:px-8">
          <div class="mx-auto max-w-3xl">
              <h2 class="text-xl font-semibold text-gray-900 dark:text-white sm:text-2xl">เพิ่มแพ็คเกจ</h2>
              <div class="mt-6 space-y-4 border-b border-t border-gray-200 py-8 dark:border-gray-700 sm:mt-8">
                  <h2 class="mb-4 text-xl font-bold text-gray-900 dark:text-white">กรอกข้อมูลแพ็คเกจ</h2>
                  <form action="#">
                      <div class="grid gap-4 sm:grid-cols-2 sm:gap-6">
                          <!-- Hotel Name -->

                          <div class="sm:col-span-2">
                              <label for="room-name"
                                     class="block mb-2 text-sm font-medium text-gray-900 dark:text-white">ชื่อแพ็คเกจ</label>
                              <input type="text"
                                     id="room-name"
                                     class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-primary-600 focus:border-primary-600 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-primary-500 dark:focus:border-primary-500"
                                     placeholder=""
                                     required>
                          </div>
                          <div class="w-full">
                  <label for="brand" class="block mb-2 text-sm font-medium text-gray-900 dark:text-white">วันที่เริ่ม</label>
                  <input type="date"
                               id="check-in-date"
                               class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-primary-600 focus:border-primary-600 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-primary-500 dark:focus:border-primary-500"
                               required>
              </div>
              <div class="w-full">
                  <label for="price" class="block mb-2 text-sm font-medium text-gray-900 dark:text-white">วันที่สิ้นสุด</label>
                  <input type="date"
                               id="check-in-date"
                               class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-primary-600 focus:border-primary-600 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-primary-500 dark:focus:border-primary-500"
                               required>
              </div>
              <div class="w-full">
                  <label for="brand" class="block mb-2 text-sm font-medium text-gray-900 dark:text-white">จำนวนวัน</label>
                  <input type="text" name="brand" id="brand" class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-primary-600 focus:border-primary-600 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-primary-500 dark:focus:border-primary-500" placeholder="" required="">
              </div>
              <div class="w-full">
                  <label for="price" class="block mb-2 text-sm font-medium text-gray-900 dark:text-white">จำนวนคืน</label>
                  <input type="text" name="brand" id="brand" class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-primary-600 focus:border-primary-600 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-primary-500 dark:focus:border-primary-500" placeholder="" required="">
              </div>

              <div class="sm:col-span-2">
                              <label for="hotel-name"
                                     class="block mb-2 text-sm font-medium text-gray-900 dark:text-white">โรมแรม</label>
                              <select id="hotel-name"
                                      class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-primary-600 focus:border-primary-600 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-primary-500 dark:focus:border-primary-500"
                                      required>
                                  <option value="Hilton">5 ดาว</option>
                                  <option value="Marriott">4 ดาว</option>
                                  <option value="Hyatt">3 ดาว</option>
                                  <option value="Sheraton">2 ดาว</option>
                                  <option value="InterContinental">1 ดาว</option>
                              </select>
                          </div>

                          <div class="sm:col-span-2">
                              <label for="hotel-name"
                                     class="block mb-2 text-sm font-medium text-gray-900 dark:text-white">สายการบิน</label>
                              <select id="hotel-name"
                                      class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-primary-600 focus:border-primary-600 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-primary-500 dark:focus:border-primary-500"
                                      required>
                                  <option value="Hilton">LionAir</option>
                                  <option value="Marriott">บางกอกแอร์เวย์ส</option>
                                  <option value="Hyatt">นกแอร์</option>
                                  <option value="Sheraton">ไทยแอร์เอเชีย</option>
                              </select>
                          </div>

                          <div class="sm:col-span-2">
                  <label for="description" class="block mb-2 text-sm font-medium text-gray-900 dark:text-white">รายละเอียดการท่องเที่ยว</label>
                  <textarea id="description" rows="8" class="block p-2.5 w-full text-sm text-gray-900 bg-gray-50 rounded-lg border border-gray-300 focus:ring-primary-500 focus:border-primary-500 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-primary-500 dark:focus:border-primary-500" placeholder="Your description here"></textarea>
              </div>
                          <!-- Check-in Date -->
                          <div class="w-full">
                  <label for="brand" class="block mb-2 text-sm font-medium text-gray-900 dark:text-white">ราคาเริ่มต้นที่</label>
                  <input type="text" name="brand" id="brand" class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-primary-600 focus:border-primary-600 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-primary-500 dark:focus:border-primary-500" placeholder="" required="">
              </div>
              <div class="w-full">
                  <label for="price" class="block mb-2 text-sm font-medium text-gray-900 dark:text-white">ลดราคาจาก</label>
                  <input type="text" name="brand" id="brand" class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-primary-600 focus:border-primary-600 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-primary-500 dark:focus:border-primary-500" placeholder="" required="">
              </div>


                          <!-- Product Image -->
                          <div class="sm:col-span-2">
                              <label for="product-image"
                                     class="block mb-2 text-sm font-medium text-gray-900 dark:text-white">เพิ่มรูปแพ็คเกจ</label>
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
                                                    d="M12 16v-4m0 0V8m0 4h4m-4 0H8m12 4v4H4v-4m16 0l-4-4m0 0l-4 4m4-4H8">
                                              </path>
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




                      </div>
                      <NuxtLink to="/hotel/back/hotelReport">
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
