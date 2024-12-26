<template>
    <UContainer>        
        <div class="relative p-4 w-full max-w-lg h-full md:h-auto">
            <div class="relative p-12 bg-white rounded-lg shadow dark:bg-gray-800 md:p-8">
                <div class="mb-4 text-sm text-center font-light text-gray-500 dark:text-gray-400">
                    <h3 class="mb-3 text-2xl font-bold text-gray-900 dark:text-white">คุณจะได้รับ</h3>
                    <p class="mb-4 font-bold text-2xl text-primary-600 dark:text-primary-500 hover:underline"> ₿ 5,000.00 </p>           
                    <!-- <p class="font-medium text-2xl text-primary-600 dark:text-primary-500 hover:underline">ยินยอมการรับ Coin ไหม?</p>            -->
                    <h3 class="mb-3 text-md font-bold text-gray-500 dark:text-white">ยินยอมการรับ Coin ไหม?</h3>
                </div>
                <div class="justify-between items-center pt-0 space-y-4 sm:flex sm:space-y-0">
                </div>
                <div class="grid grid-cols-2 gap-4">
                            <UButton to="/coinApp/home"
                                     class="flex justify-center"
                                     color="white">ยกเลิก</UButton>
                            <UButton to="/coinApp/successReceive1"
                            class="flex justify-center"
                                     >ยืนยัน</UButton>
                        </div>
            </div>
        </div>
    </UContainer>
</template>