<script setup lang="ts">
import type { NavItem } from '@nuxt/content'

const navigation = inject<Ref<NavItem[]>>('navigation', ref([]))

const links = [{
  label: 'สินค้าและบริการทั้งหมด',
  to: '/ecommerce/home'
}, {
  label: 'ลงขายสินค้า',
  to: '/ecommerce/registerProduct'
}, {
  label: 'สินค้าที่ลงทะเบียน',
  to: '/ecommerce/productPreView'
}, {
  label: 'คลังสินค้า',
  to: '/ecommerce/stock'
}]
</script>

<template>
  <UHeader :links="links">
    <template #logo>
      Nuxt UI Pro <UBadge
        label="SaaS"
        variant="subtle"
        class="mb-0.5"
      />
    </template>

    <template #right>
      <UButton
        label="Sign in"
        color="gray"
        to="/login"
      />
      <UButton
        label="Sign up"
        icon="i-heroicons-arrow-right-20-solid"
        trailing
        color="black"
        to="/signup"
        class="hidden lg:flex"
      />
    </template>

    <template #panel>
      <UNavigationTree
        :links="mapContentNavigation(navigation)"
        default-open
      />
    </template>
  </UHeader>
</template>
