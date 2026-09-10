<script setup>
const logoUrl = `${import.meta.env.BASE_URL}revsys-logo.png`
</script>

<template>
  <div class="slidev-layout revsys-slide revsys-content">
    <slot />
    <div v-if="$slots.left || $slots.right" class="revsys-columns">
      <div><slot name="left" /></div>
      <div><slot name="right" /></div>
    </div>
    <img class="revsys-content-logo" :src="logoUrl" alt="REVSYS" />
  </div>
</template>
