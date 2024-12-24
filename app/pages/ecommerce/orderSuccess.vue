<template>
    <UContainer>
        <section class="bg-white py-8 antialiased dark:bg-gray-900 md:py-16">
            <div class="mx-auto max-w-2xl px-4 2xl:px-0">
                <h2 class="text-xl font-semibold text-gray-900 dark:text-white sm:text-2xl mb-2">
                    ขอบคุณสำหรับการสั่งซื้อของคุณ!
                </h2>
                <p class="text-gray-500 dark:text-gray-400 mb-6 md:mb-8">คำสั่งซื้อ หมายเลข <a href="#"
                       class="font-medium text-gray-900 dark:text-white hover:underline">#7564804</a>
                    ของคุณจะได้รับการดำเนินการภายใน 24 ชั่วโมงในวันทำการ
                    เราจะแจ้งให้คุณทราบทางอีเมลเมื่อคำสั่งซื้อของคุณได้รับการจัดส่งแล้ว
                </p>
                <div
                     class="space-y-4 sm:space-y-2 rounded-lg border border-gray-100 bg-gray-50 p-6 dark:border-gray-700 dark:bg-gray-800 mb-6 md:mb-8">
                    <dl class="sm:flex items-center justify-between gap-4">
                        <dt class="font-normal mb-1 sm:mb-0 text-gray-500 dark:text-gray-400">วันที่</dt>
                        <dd class="font-medium text-gray-900 dark:text-white sm:text-end">{{ new Date().toLocaleDateString('en-US', { year: 'numeric', month: 'short', day: 'numeric' }) }}</dd>

                    </dl>
                    <dl class="sm:flex items-center justify-between gap-4">
                        <dt class="font-normal mb-1 sm:mb-0 text-gray-500 dark:text-gray-400">วิธีการชำระเงิน</dt>
                        <dd class="font-medium text-gray-900 dark:text-white sm:text-end">ชำระด้วย KGO Coin
                        </dd>
                    </dl>
                    <dl class="sm:flex items-center justify-between gap-4">
                        <dt class="font-normal mb-1 sm:mb-0 text-gray-500 dark:text-gray-400">ชื่อ</dt>
                        <dd class="font-medium text-gray-900 dark:text-white sm:text-end">Somchai Sittipong</dd>
                    </dl>
                    <dl class="sm:flex items-center justify-between gap-4">
                        <dt class="font-normal mb-1 sm:mb-0 text-gray-500 dark:text-gray-400">ที่อยู่</dt>
                        <dd class="font-medium text-gray-900 dark:text-white sm:text-end">Lao PDR, Vientiane, 1234, Lane Xang Avenue
                        </dd>
                    </dl>
                    <dl class="sm:flex items-center justify-between gap-4">
                        <dt class="font-normal mb-1 sm:mb-0 text-gray-500 dark:text-gray-400">โทรศัพท์</dt>
                        <dd class="font-medium text-gray-900 dark:text-white sm:text-end">+(123) 456 7890</dd>
                    </dl>
                </div>
                <div class="flex items-center space-x-4">
                    <UButton to="/ecommerce/orderTracking"
                       class="text-white bg-primary-700 hover:bg-primary-800 focus:ring-4 focus:ring-primary-300 font-medium rounded-lg text-sm px-5 py-2.5 dark:bg-primary-600 dark:hover:bg-primary-700 focus:outline-none dark:focus:ring-primary-800">ติดตามคำสั่งซื้อของคุณ</UButton>
                    <UButton to="/ecommerce/products"
                       class="py-2.5 px-5 text-sm font-medium text-gray-900 focus:outline-none bg-white rounded-lg border border-gray-200 hover:bg-gray-100 hover:text-primary-700 focus:z-10 focus:ring-4 focus:ring-gray-100 dark:focus:ring-gray-700 dark:bg-gray-800 dark:text-gray-400 dark:border-gray-600 dark:hover:text-white dark:hover:bg-gray-700">สั่งสินค้าเพิ่มเติ่ม</UButton>
                </div>
            </div>
        </section>
    </UContainer>
</template>