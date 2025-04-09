<template>
  <section class="py-8 bg-white md:py-16 dark:bg-gray-900 antialiased">
    <div class="max-w-screen-xl px-4 mx-auto 2xl:px-0">
      <div class="lg:grid lg:grid-cols-2 lg:gap-8 xl:gap-16">
        <section class="bg-white dark:bg-gray-900">
  <div class=" mx-auto max-w-2xl ">
      <h2 class="mb-4 text-xl font-bold text-gray-900 dark:text-white">กรอกรายละเอียดการจอง</h2>
      <form action="#">
          <div class="grid gap-4 sm:grid-cols-2 sm:gap-6">
              <div class="sm:col-span-2">
                <label for="category" class="block mb-2 text-sm font-medium text-gray-900 dark:text-white">เลือกวันเดินทาง*</label>
                  <select id="category" class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-primary-500 focus:border-primary-500 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-primary-500 dark:focus:border-primary-500">
                      <option selected="">เลือกวันเดินทาง</option>
                      <option value="TV">พ.ค. 68 - มิ.ย. 68</option>
                  </select>
              </div>
              <div class="w-full">
                  <label for="brand" class="block mb-2 text-sm font-medium text-gray-900 dark:text-white">ชื่อผู้ติดต่อ*</label>
                  <input type="text" name="brand" id="brand" class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-primary-600 focus:border-primary-600 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-primary-500 dark:focus:border-primary-500" placeholder="" required="">
              </div>
              <div class="w-full">
                  <label for="price" class="block mb-2 text-sm font-medium text-gray-900 dark:text-white">นามสกุล*</label>
                  <input type="text" name="brand" id="brand" class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-primary-600 focus:border-primary-600 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-primary-500 dark:focus:border-primary-500" placeholder="" required="">
              </div>
              <div class="w-full">
                  <label for="price" class="block mb-2 text-sm font-medium text-gray-900 dark:text-white">เบอร์โทรติดต่อ*</label>
                  <input type="text" name="brand" id="brand" class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-primary-600 focus:border-primary-600 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-primary-500 dark:focus:border-primary-500" placeholder="" required="">
              </div>
              <div class="w-full">
                  <label for="price" class="block mb-2 text-sm font-medium text-gray-900 dark:text-white">อีเมล*</label>
                  <input type="text" name="brand" id="brand" class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-primary-600 focus:border-primary-600 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-primary-500 dark:focus:border-primary-500" placeholder="" required="">
              </div>
              <div class="sm:col-span-2">
                  <label for="description" class="block mb-2 text-sm font-medium text-gray-900 dark:text-white">ความต้องการพิเศษ</label>
                  <textarea id="description" rows="8" class="block p-2.5 w-full text-sm text-gray-900 bg-gray-50 rounded-lg border border-gray-300 focus:ring-primary-500 focus:border-primary-500 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-primary-500 dark:focus:border-primary-500" placeholder="Your description here"></textarea>
              </div>
          </div>
            <NuxtLink to="/packageTour/home" class="inline-flex items-center px-5 py-2.5 mt-4 sm:mt-6 text-sm font-medium text-center text-white bg-primary-700 rounded-lg focus:ring-4 focus:ring-primary-200 dark:focus:ring-primary-900 hover:bg-primary-800">
              ยืนยันการจอง
            </NuxtLink>
            <NuxtLink to="/packageTour/detail" class="ml-3 inline-flex items-center px-5 py-2.5 mt-4 sm:mt-6 text-sm font-medium text-center text-white bg-red-700 rounded-lg focus:ring-4 focus:ring-red-200 dark:focus:ring-red-900 hover:bg-red-800">
              ยกเลิกการจอง
            </NuxtLink>
      </form>
  </div>
</section>

        <div class="shrink-0 max-w-md lg:max-w-lg mx-auto">
          <a href="#" class="block w-full max-w-lg p-2 bg-white border border-gray-200 rounded-lg shadow-lg">
              <div class="flex justify-between items-center ">
                <img class="w-1/5 dark:hidden" src="https://www.planetholidaystravel.com/wp-content/uploads/2025/04/banner-JSL221_310325-110800-1.jpg" alt="" />
                <p class="ml-3 font-bold text-xl">ทัวร์ญี่ปุ่น ช้อปปิ้ง ชิลล์ โตเกียว ชินจูกุ อาซากุสะ นาริตะ โอไดบะ (SL) </p>
              </div>
          </a>

            <a href="#" class="block w-full max-w-lg p-8 bg-white border border-gray-200 rounded-lg shadow-lg mt-2">
              <div class="flex justify-start items-center ">
                <UIcon name="i-heroicons-exclamation-circle" class="mr-2 text-4xl mb-4"  />
                <h5 class="mb-4 text-3xl font-bold tracking-tight text-gray-600 dark:text-white"> เงื่อนไขการจองทัวร์</h5>
              </div>
            <p class="text-gray-500 dark:text-gray-400 mb-2">
              1. การจองทัวร์นี้ยังไม่ใช่การคอนเฟิร์มที่นั่งทันที กรุณารอการตอบกลับจากเจ้าหน้าที่เท่านั้น
            </p>
            <p class="text-gray-500 dark:text-gray-400 mb-2">
              2. หากลูกค้าจองทัวร์ในช่วงวันจันทร์-ศุกร์ เวลา 09.00 น-18.00 น หากระยะเวลาจองผ่านมากกว่า 30 นาทีและยังไม่มีเจ้าหน้าที่ติดต่อกลับ รบกวนลูกค้าแจ้งมาที่ไลน์ @planetholiday หรือโทร 02-530-9899, 081-855-7999, 081-839-0999 พร้อมแจ้งรหัสการจอง
            </p>
            <p class="text-gray-500 dark:text-gray-400 mb-2">
              3. ลูกค้าสามารถเปลี่ยนแปลงวันที่เดินทางได้ กรุณาติดต่อพนักงานขายที่ท่านจอง
            </p>
            <p class="text-gray-500 dark:text-gray-400 mb-2">
              4. บริษัทฯ ขอสงวนสิทธิ์ในการยกเลิกการจอง ในกรณีที่นั่งเต็ม หรือทัวร์ไม่คอนเฟิร์มออกเดินทาง ระยะเวลาในการใช้ส่วนลดเป็นไปตามที่บริษัทฯ กำหนด
            </p>
            <p class="text-gray-500 dark:text-gray-400 mb-2">
              5. ส่วนลดพิเศษจะใช้ได้ต่อเมื่อได้รับการยืนยันจากเจ้าหน้าที่เท่านั้น
            </p>
            <p class="text-gray-500 dark:text-gray-400 mb-2">
              6. การจองจะเสร็จสมบูรณ์ในกรณีที่ลูกค้าได้รับการยืนยันที่นั่งเป็นเอกสารและลูกค้าได้ชำระยอดเงินเท่านั้น
            </p>
            <p class="text-gray-500 dark:text-gray-400">
              7. บริษัทฯ ขอสงวนสิทธิ์ในการเปลี่ยนแปลงข้อกำหนดและเงื่อนไขต่าง ๆ ของส่วนลดพิเศษโดยมิต้องแจ้งให้ทราบล่วงหน้า
            </p>
          </a>

        </div>
      </div>
    </div>
  </section>
</template>
