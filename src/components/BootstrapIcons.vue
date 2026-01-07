<script setup>
defineProps(['icon'])
defineEmits(['iconClick'])
</script>

<template>
  <i
    :class="`bi bi-${icon}`"
    @click="$emit('iconClick')"
  />
</template>

<!-- 
<style scoped>
 @import "bootstrap-icons";
</style> 
-->
