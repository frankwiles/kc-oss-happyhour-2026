<script setup>
import { computed } from 'vue'
import { useIsSlideActive, useSlideContext } from '@slidev/client'

const isActive = useIsSlideActive()
const { $renderContext } = useSlideContext()
const falling = computed(() => isActive.value && ['slide', 'presenter'].includes($renderContext.value))
const bloodUrl = `${import.meta.env.BASE_URL}blood-drips.svg`
</script>

<template>
  <img class="revsys-blood-drips" :src="bloodUrl" alt="" aria-hidden="true" />
  <svg
    class="blood-droplets"
    :class="{ falling }"
    viewBox="0 0 980 551.25"
    preserveAspectRatio="none"
    aria-hidden="true"
  >
    <g fill="#b01b2c">
      <path class="droplet droplet-first" d="M339 137 C337 144 331 150 331 156 A8 8 0 0 0 347 156 C347 150 341 144 339 137Z" />
      <path class="droplet droplet-second" d="M919 131 C917 138 912 144 912 149 A7 7 0 0 0 926 149 C926 144 921 138 919 131Z" />
    </g>
  </svg>
</template>

<style scoped>
.blood-droplets {
  position: absolute;
  inset: 0;
  width: 100%;
  height: 100%;
  overflow: hidden;
  pointer-events: none;
  z-index: 1;
}

.falling .droplet {
  animation: blood-drop 1.65s cubic-bezier(0.42, 0, 1, 1) forwards;
}

.falling .droplet-first {
  animation-delay: 0.4s;
}

.falling .droplet-second {
  animation-delay: 0.85s;
}

@keyframes blood-drop {
  from { transform: translateY(0); }
  to { transform: translateY(560px); }
}

@media (prefers-reduced-motion: reduce), print {
  .falling .droplet {
    animation: none;
  }
}
</style>
