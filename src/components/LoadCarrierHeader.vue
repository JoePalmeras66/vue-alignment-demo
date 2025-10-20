<template>
  <div class="header" :class="`align-${position}`">
    <div class="header-item">
      <slot name="item">
        <div class="default-item">📦</div>
      </slot>
    </div>
    <div class="header-text">
      <slot name="text">
        <h3>Load Carrier Header</h3>
      </slot>
    </div>
  </div>
</template>

<script setup lang="ts">
import { defineProps } from 'vue';

type Position = 'top' | 'left' | 'right';

defineProps<{
  position: Position;
}>();
</script>

<style scoped>
.header {
  display: flex;
  gap: 1rem;
  padding: 1rem;
  background: #e3f2fd;
  border-radius: 8px;
}

.align-top {
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
}

.align-left {
  flex-direction: column;
  align-items: flex-start;
}

.align-right {
  flex-direction: column;
  align-items: flex-end;
}

.header-text {
  text-align: inherit;
}

.header-text h3 {
  margin: 0;
  color: #1976d2;
}

.default-item {
  font-size: 2rem;
}
</style>
