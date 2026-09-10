<script setup>
const logoUrl = `${import.meta.env.BASE_URL}revsys-logo.png`
</script>

<template>
  <div class="slidev-layout revsys-slide revsys-title">
    <img class="revsys-title-logo" :src="logoUrl" alt="REVSYS" />
    <div class="revsys-title-copy">
      <slot />
      <div v-if="$slots.footer" class="revsys-title-footer">
        <slot name="footer" />
      </div>
    </div>
  </div>
</template>
