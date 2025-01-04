<script setup lang="ts">

</script>

<template>
    <UContainer>
        <section class="bg-white dark:bg-gray-900">
            <div class="py-8 px-4 mx-auto max-w-screen-xl sm:py-16 lg:px-6">
                <div class="mx-auto max-w-screen-sm text-center">
                    <h2 class="mb-4 text-4xl tracking-tight font-extrabold leading-tight text-gray-900 dark:text-white">
                        QR Code</h2>
                        <p class="mb-6 font-light text-gray-500 dark:text-gray-400 md:text-lg">สแกนจ่ายเงิน</p>
                        <UCard>
                    <NuxtLink to="/cfOrder/orderSuccess">
                            <img src="https://flowbite.s3.amazonaws.com/blocks/marketing-ui/cta/qr-code.svg"
                                 alt="QR Code"
                                 class="mx-auto"
                                 width="400"
                                 height="400">
                                </NuxtLink>
                            </UCard>
                                <div class="flex justify-center mt-4">
                                    <UButton @click="downloadQRCode"
                                    icon="i-material-symbols-download"
                                    class="flex items-center justify-center ">
                                    Save QR Code</UButton>
                                </div>
                            </div>
            </div>
        </section>
    </UContainer>
</template>