<script setup lang="ts">
import type { NavItem } from '@nuxt/content'

const navigation = inject<Ref<NavItem[]>>('navigation', ref([]))

const links = [{
  label: 'NaLoei',
  to: '/ecommerce/home',
  children: [{
    label: 'สินค้าและบริการทั้งหมด',
    to: '/ecommerce/home',
  }, {
    label: 'คลังสินค้า NaLoei',
    to: '/ecommerce/stock',
  }, {
    label: 'ตลาดซื้อขาย',
    to: '/ecommerce/productPreView2',
  }, {
    label: 'บริการอื่น ๆ',
    to: '/NaLoeiWeb/home'
  }, {
    label: 'รายได้จากการขาย',
    to: '/NaLoeiWeb/financeStock'
  }]
}, {
  label: 'สวนผู้ขาย',
  to: '/ecommerce/registerStore',
  children: [{
    label: 'ลงทะเบียนร้านค้า',
    to: '/ecommerce/registerStore',
  }, {
    label: 'สินค้าที่สวนลงขาย',
    to: '/ecommerce/productPreView',
  }, {
    label: 'ลงขายสินค้า',
    to: '/ecommerce/registerProduct',
  }]
}, {
  label: 'โรงแรม',
  to: '/hotel/back/hotelReport',
  children: [
    {
      label: 'ติดต่อบริการ',
      to: '/hotel/naloei/hotelSale'
    }, {
      label: 'จัดการห้องพัก',
      to: '/hotel/back/hotelReport',
    }, {
      label: 'ลงทะเบียนห้องพัก',
      to: '/hotel/back/hotelRegister',
    }]
}, {
  label: 'รถให้เช่า',
  to: '/NaLoeiWeb/carBooking',
  children: [
    {
      label: 'รถให้เช่า',
      to: '/NaLoeiWeb/carBooking',
    }, {
      label: 'จัดการรถให้เช่า',
      to: '/car/back/carReport',
    }, {
      label: 'ลงทะเบียนรถให้เช่า',
      to: '/car/back/carRegister',
    }]
}, {
  label: 'แพ็กเกจทัวร์',
  to: '/packageTour/home',
  children: [
    {
      label: 'แพ็กเกจทัวร์',
      to: '/packageTour/home',
    }, {
      label: 'จัดการแพ็กเกจทัวร์',
      to: '/packagetour/reportpackage',
    }, {
      label: 'ลงทะเบียนแพ็กเกจทัวร์',
      to: '/packagetour/createpackage',
    }]
}]
</script>

<template>
  <UHeader :links="links">
    <template #logo>
      Nuxt UI Pro
      <UBadge label="SaaS"
        variant="subtle"
        class="mb-0.5" />
    </template>

    <template #right>
      <UButton label="Sign in"
        color="gray"
        to="/login" />
      <UButton label="Sign up"
        icon="i-heroicons-arrow-right-20-solid"
        trailing
        color="black"
        to="/signup"
        class="hidden lg:flex" />
    </template>

    <template #panel>
      <UNavigationTree :links="mapContentNavigation(navigation)"
        default-open />
    </template>
  </UHeader>
</template>
