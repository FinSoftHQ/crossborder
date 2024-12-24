<template>
<div class="relative p-12 w-full max-w-md h-full md:h-auto">    
    <div class="relative p-8 text-center bg-white">        
        <div class="w-12 h-12 flex items-center justify-center mx-auto mb-3.5">
            <svg 
            class="w-12 h-12 text-green-500 dark:text-green-400"xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24"><rect width="24" height="24" fill="none"/><g fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2"><path fill="currentColor" fill-opacity="0.3" d="M3 12c0 -4.97 4.03 -9 9 -9c4.97 0 9 4.03 9 9c0 4.97 -4.03 9 -9 9c-4.97 0 -9 -4.03 -9 -9Z"><animate fill="freeze" attributeName="fill-opacity" dur="0.15s" values="0.3;0"/></path><path stroke-dasharray="14" stroke-dashoffset="14" d="M8 12l3 3l5 -5"><animate fill="freeze" attributeName="stroke-dashoffset" begin="0.15s" dur="0.2s" values="14;0"/></path></g></svg>
            <span class="sr-only">Success</span>
        </div>
        <p class="mb-4 text-lg font-semibold text-gray-900 dark:text-white">ดำเนินการจ่ายเสร็จสิ้น</p>
        <UButton  to="/coinApp/home" class="">
            กลับไปหน้าแรก
        </UButton>
    </div>

</div>
</template>