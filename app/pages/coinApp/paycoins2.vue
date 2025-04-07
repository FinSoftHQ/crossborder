<script setup lang="ts">
import { ref, reactive } from 'vue';

const items = [
    {
        slot: 'scan',
        label: 'สแกนรับ/จ่าย',
        icon: 'i-bx-scan',
    },
]

const accountForm = reactive({ name: 'Benjamin', username: 'benjamincanac' })
const passwordForm = reactive({ currentPassword: '', newPassword: '' })

const showFooter = ref(false);

function onSubmitAccount() {
    console.log('Submitted form:', accountForm)
}

function onSubmitPassword() {
    console.log('Submitted form:', passwordForm)
}

const loading = ref(false);

function generateQRCode() {
    loading.value = true;
    showFooter.value = true;
    setTimeout(() => {
        loading.value = false;
    }, 500); // Simulate QR code generation delay
}
function copyToClipboard() {
    const copyText = "https://flowbite.s3.amazonaws.com/blocks/marketing-ui/cta/qr-code.svg";
    navigator.clipboard.writeText(copyText).then(() => {
        console.log('Copied to clipboard:', copyText);
    }).catch(err => {
        console.error('Failed to copy:', err);
    });
}
</script>

<template>
    <UContainer>
        <UTabs :items="items"
               class="w-full">
            <template #scan="{ item }">
                <UCard @submit.prevent="onSubmitAccount">
                    <template #header>
                        <p class="text-base font-semibold leading-6 text-gray-900 dark:text-white">
                            {{ item.label }}
                        </p>
                        <p class="mt-1 text-sm text-gray-500 dark:text-gray-400">
                            สแกน QR Code เพื่อรับ Coin จากเพื่อน หรือ จ่าย Coin
                        </p>
                    </template>

                    <div class="flex justify-center items-center">
                        <NuxtLink to="/coinApp/successpay">
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
                    <!-- <template #footer>
                        <UButton type="submit">
                            บันทึก QR Code
                        </UButton>
                    </template> -->
                </UCard>
            </template>
           
        </UTabs>
    </UContainer>
</template>