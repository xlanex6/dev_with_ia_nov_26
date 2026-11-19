<script setup lang="ts">
import { useNav } from '@slidev/client'

const { currentPage, total } = useNav()

function pad(n: number) {
  return String(n).padStart(2, '0')
}
</script>

<template>
  <div class="wrap-chrome pointer-events-none">
    <img
      src="/avatar.jpeg"
      alt=""
      class="wrap-chrome__avatar"
      width="36"
      height="36"
    >
    <div class="wrap-chrome__count">
      {{ pad(currentPage) }} / {{ pad(total) }}
    </div>
  </div>
</template>

<style scoped>
.wrap-chrome {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  z-index: 20;
  padding: 24px 32px;
  display: flex;
  align-items: flex-start;
  justify-content: space-between;
  font-family: 'Avenir Pro', 'Avenir', 'Avenir Next', system-ui, sans-serif;
}

.wrap-chrome__avatar {
  width: 36px;
  height: 36px;
  border-radius: 50%;
  object-fit: cover;
  border: 1px solid color-mix(in srgb, #0d0a3d 16%, transparent);
  filter: grayscale(100%);
}

.wrap-chrome__count {
  font-size: 12px;
  font-weight: 600;
  letter-spacing: 0.14em;
  color: #2a1eff;
  text-transform: lowercase;
}
</style>