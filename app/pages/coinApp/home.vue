<script setup lang="ts">
const modules = [{
    title: 'รับ Coin',
    to: '/coinApp/coinReceive',
    icon: 'i-lucide-scan-line'
}, 
{
    title: 'จ่าย Coin',
    to: '/coinApp/paycoins',
    icon: 'i-streamline-coin-share'
},
{
    title: 'โอน Coin',
    to: '/coinApp/transferCoin',
    icon: 'i-streamline-coin-share'
},
    // {
    //     title: 'Tailwind CSS',
    //     description: 'Add Tailwind CSS to your Nuxt application in seconds with PurgeCSS included for minimal CSS.',
    //     to: 'https://github.com/nuxt-modules/tailwindcss',
    //     icon: 'i-simple-icons-tailwindcss'
    // }
]
</script>
<template>
    <UContainer>
        <section class="bg-white py-4 antialiased dark:bg-gray-900 md:py-16">
            <div class="space-y-4 mb-4">
                <h3 class="text-xl font-semibold text-gray-900 dark:text-white">Wallet</h3>
                <UCard>
                    <div class="flex flex-col gap-4 ">
                        <UIcon name="i-ion-wallet"
                               class="h-10 w-10 text-sky-500 dark:text-blue-400 " />

                        <label for="credit-card"
                               class="font-medium leading-none text-gray-900 dark:text-white">
                            ยอด Coin ทั้งหมด</label>
            <label class="flex items-center gap-2 font-bold text-xl leading-none text-gray-900 dark:text-white">               
                <!-- <UIcon name="i-ri-bit-coin-line" class="h-5 w-5 text-gray-800 dark:text-gray-400" />  -->
                ₿ 9,000
            </label>
                        <!-- <p id="credit-card-text"
                           class="mt-1 text-xs font-normal text-gray-500 dark:text-gray-400"> Coin ทั้งหมดของคุณ</p> -->
                    </div>
                </UCard>
            </div>
            <UPageGrid class="grid grid-cols-2 gap-4 mt-8">
                <UPageCard v-for="(module, index) in modules"
                           :key="index"
                           v-bind="module">
                    <template #description>
                        <span class="line-clamp-2">{{ module.description }}</span>
                    </template>
                </UPageCard>
            </UPageGrid>
        </section>
    </UContainer>
</template>