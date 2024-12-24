<script setup lang="ts">
import { ref, reactive } from 'vue';

const items = [{
    slot: 'scan',
    label: 'สแกน QR Code',
    icon: 'i-bx-scan',
}, {
    slot: 'share',
    label: 'Share Coin KGO',
    icon: 'i-mdi-light-share',
    label: 'แบ่งบัน Coin KGO',
    icon: 'i-mdi-light-share',
}]

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
                    </div>                 
                    <!-- <template #footer>
                        <UButton type="submit">
                            บันทึก QR Code
                        </UButton>
                    </template> -->
                </UCard>
            </template>

            <template #share="{ item }">
                <UCard @submit.prevent="onSubmitPassword">
                    <template #header>
                        <h3 class="text-base font-semibold leading-6 text-gray-900 dark:text-white">
                            แบ่งบัน Coin KGO
                        </h3>
                        <p class="mt-1 text-sm text-gray-500 dark:text-gray-400">
                            แบ่งบัน Coin ของคุณ หรือสร้างคิวอาร์โค้ดแล้วส่งให้เพื่อน
                        </p>
                    </template>

                    <UFormGroup label="จำนวน Coin ที่ต้องการ"
                                placeholder="$0.00"
                                required
                                class="mb-3">
                        <UInput v-model="passwordForm.currentPassword"
                                type="password"
                                required />
                    </UFormGroup>
                    <UFormGroup label="ข้อความ"
                                required>
                        <UInput v-model="passwordForm.newPassword"
                                type="password" />
                    </UFormGroup>
                    <div class="grid grid-cols-1 gap-4 mt-4 mb-4">
                        <UButton class="flex justify-center"
                                 @click="generateQRCode">สร้าง QR Code</UButton>
                    </div>



                    <template v-if="showFooter"
                              #footer>
                        <div class="flex flex-col gap-4">
                            <UCard>
                                <div v-if="loading"
                                     role="status"
                                     class="flex items-center justify-center w-full h-56 dark:bg-gray-800">
                                    <span class="sr-only">Loading...</span>
                                    <svg aria-hidden="true"
                                         class="w-8 h-8 text-gray-200 animate-spin dark:text-gray-600 fill-blue-600"
                                         viewBox="0 0 100 101"
                                         fill="none"
                                         xmlns="http://www.w3.org/2000/svg">
                                        <path d="M100 50.5908C100 78.2051 77.6142 100.591 50 100.591C22.3858 100.591 0 78.2051 0 50.5908C0 22.9766 22.3858 0.59082 50 0.59082C77.6142 0.59082 100 22.9766 100 50.5908ZM9.08144 50.5908C9.08144 73.1895 27.4013 91.5094 50 91.5094C72.5987 91.5094 90.9186 73.1895 90.9186 50.5908C90.9186 27.9921 72.5987 9.67226 50 9.67226C27.4013 9.67226 9.08144 27.9921 9.08144 50.5908Z"
                                              fill="currentColor" />
                                        <path d="M93.9676 39.0409C96.393 38.4038 97.8624 35.9116 97.0079 33.5539C95.2932 28.8227 92.871 24.3692 89.8167 20.348C85.8452 15.1192 80.8826 10.7238 75.2124 7.41289C69.5422 4.10194 63.2754 1.94025 56.7698 1.05124C51.7666 0.367541 46.6976 0.446843 41.7345 1.27873C39.2613 1.69328 37.813 4.19778 38.4501 6.62326C39.0873 9.04874 41.5694 10.4717 44.0505 10.1071C47.8511 9.54855 51.7191 9.52689 55.5402 10.0491C60.8642 10.7766 65.9928 12.5457 70.6331 15.2552C75.2735 17.9648 79.3347 21.5619 82.5849 25.841C84.9175 28.9121 86.7997 32.2913 88.1811 35.8758C89.083 38.2158 91.5421 39.6781 93.9676 39.0409Z"
                                              fill="currentFill" />
                                    </svg>
                                </div>
                                <img v-else
                                     src="https://flowbite.s3.amazonaws.com/blocks/marketing-ui/cta/qr-code.svg"
                                     alt="QR Code"
                                     class="mx-auto"
                                     width="200"
                                     height="auto">
                            </UCard>
                        </div>
                        <div class="flex flex-col gap-4 mt-4">
                            <p id="credit-card-text"
                               class="text-center text-sm font-medium text-gray-900 dark:text-white block">
                                คัดลอกหรือแชร์ลิงก์นี้เพื่อแบ่งบัน Coin
                            </p>
                            <div class="px-4 pb-4 md:px-5 md:pb-5">
                                <div class="relative mb-4">
                                    <input id="course-url"
                                           type="text"
                                           class="col-span-6 bg-gray-50 border border-gray-300 text-gray-500 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-gray-400 dark:focus:ring-blue-500 dark:focus:border-blue-500"
                                           value="https://flowbite.s3.amazonaws.com/blocks/marketing-ui/cta/qr-code.svg"
                                           disabled
                                           readonly>
                                    <button @click="copyToClipboard"
                                            data-tooltip-target="tooltip-course-url"
                                            class="absolute end-2 top-1/2 -translate-y-1/2 text-gray-500 dark:text-gray-400 hover:bg-gray-100 dark:hover:bg-gray-800 rounded-lg p-2 inline-flex items-center justify-center">
                                        <span id="success-icon-course-url"
                                              class="hidden inline-flex items-center">
                                            <svg class="w-3.5 h-3.5 text-blue-700 dark:text-blue-500"
                                                 aria-hidden="true"
                                                 xmlns="http://www.w3.org/2000/svg"
                                                 fill="none"
                                                 viewBox="0 0 16 12">
                                                <path stroke="currentColor"
                                                      stroke-linecap="round"
                                                      stroke-linejoin="round"
                                                      stroke-width="2"
                                                      d="M1 5.917 5.724 10.5 15 1.5" />
                                            </svg>
                                        </span>
                                    </button>
                                    <div id="tooltip-course-url"
                                         role="tooltip"
                                         class="absolute z-10 invisible inline-block px-3 py-2 text-sm font-medium text-white transition-opacity duration-300 bg-gray-900 rounded-lg shadow-sm opacity-0 tooltip dark:bg-gray-700">
                                        <span id="default-tooltip-message-course-url">Copy to clipboard</span>
                                        <span id="success-tooltip-message-course-url"
                                              class="hidden">Copied!</span>
                                        <div class="tooltip-arrow"
                                             data-popper-arrow></div>
                                    </div>
                                </div>
                                <div class="grid grid-cols-2 gap-4">
                                    <UButton class="flex justify-center"
                                             color="white"
                                             @click="copyToClipboard">คัดลอกลิงก์</UButton>
                                    <UButton class="flex justify-center">แชร์ลิงก์</UButton>
                                </div>
                            </div>
                        </div>

                    </template>
                </UCard>
            </template>
        </UTabs>
    </UContainer>
</template>