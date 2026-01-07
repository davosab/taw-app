<script setup>
import FullName from '@/components/computed/FullName.vue';
import PriceCalculator from '@/components/computed/PriceCalculator.vue';
import SupplierList from '@/components/computed/SupplierList.vue';

import { ref } from "vue";
const fullName = ref("");
const totalPrice = ref("");
</script>

<template>
  <h2 class="text-xl font-bold">
    Test Computed in VueJs
  </h2>
  <FullName @update:full-name="fN => fullName = fN" />
  <p>Your full name from parent component: {{ fullName }}</p>
  <hr class="my-4">
  <PriceCalculator @update:total-price="tp => totalPrice = tp" />
  <hr class="my-4">
  <SupplierList
    :full-name="fullName"
    :total-price="totalPrice"
  />
</template>
 
<style>
 @import "bootstrap-icons";
 @import "tailwindcss";
</style>
