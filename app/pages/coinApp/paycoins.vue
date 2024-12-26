<template><div lass="hidden overflow-y-auto overflow-x-hidden fixed top-0 right-0 left-0 z-50 justify-center items-center w-full md:inset-0 h-modal md:h-full">
    <div class="relative p-4 w-full max-w-2xl h-full md:h-auto">
        <div class="relative p-4 bg-white rounded-lg shadow dark:bg-gray-800 sm:p-5 border-1">
            <div class="flex justify-between items-center pb-4 mb-4 rounded-t border-b sm:mb-5 dark:border-gray-600">
                <h3 class="text-lg font-semibold text-gray-900 dark:text-white">
                    จ่าย Coin
                    <p class="text-base font-semibold leading-6 text-gray-900 dark:text-white">
                            
                        </p>
                        <p class="mt-1 text-sm text-gray-500 dark:text-gray-400">
                            สแกน QR Code เพื่อรับ Coin จากเพื่อน หรือ จ่าย Coin
                        </p>
                </h3>              
            </div>
            <div class="flex justify-center items-center">
                        <NuxtLink to="/coinApp/paycoins1">
                        <svg class="w-[250px] h-auto text-gray-500 dark:text-gray-400"
                             xmlns="http://www.w3.org/2000/svg"
                             width="24"
                             height="24"
                             viewBox="0 0 24 24">
                            <rect width="24"
                                  height="24"
                                  fill="none" />
                            <path fill="none"
                                  stroke="currentColor"
                                  stroke-linecap="round"
                                  stroke-linejoin="round"
                                  stroke-width="1"
                                  d="M3 7V5a2 2 0 0 1 2-2h2m10 0h2a2 2 0 0 1 2 2v2m0 10v2a2 2 0 0 1-2 2h-2M7 21H5a2 2 0 0 1-2-2v-2" />
                        </svg>
                    </NuxtLink>
                    </div>
        </div>
    </div>
</div>
</template>