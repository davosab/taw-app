<script setup>
 import InputCurrency from '@/components/InputCurrency.vue'

 import { ref } from 'vue'
 const currencyEUR = ref(0);
 const currencyRON = ref(0);
 const cursEURRON = ref(4.9);

 const computeEURToRON = (value) => {
   currencyEUR.value = value;
   currencyRON.value = (value * cursEURRON.value).toFixed(2);
 };
const computeRONToEUR = (value) => {
   currencyRON.value = value;
   currencyEUR.value = (value / cursEURRON.value).toFixed(2);
 };
 const recalculateCurrency = () => {
    computeRONToEUR(currencyRON.value);
    computeEURToRON(currencyEUR.value);
 }
</script>

<template>
  <h3>Currency Converter</h3>
  <InputCurrency
    :value="currencyEUR"
    @change-value="computeEURToRON"
  />
  <input
    v-model="cursEURRON"
    type="number"
    @input="recalculateCurrency"
  >
  <InputCurrency
    :value="currencyRON"
    @change-value="computeRONToEUR"
  />
</template>