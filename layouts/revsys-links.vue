<script setup>
import RevsysContent from './revsys-content.vue'
</script>

<template>
  <RevsysContent class="revsys-links">
    <slot />
    <template v-if="$slots.left" #left><slot name="left" /></template>
    <template v-if="$slots.right" #right><slot name="right" /></template>
  </RevsysContent>
</template>

<style>
.slidev-layout.revsys-links a,
.slidev-layout.revsys-links a:hover,
.slidev-layout.revsys-links a:focus,
.slidev-layout.revsys-links a:visited {
  color: #000;
  text-decoration: none;
  border-bottom: none;
}
</style>
