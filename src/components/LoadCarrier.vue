<template>
  <div class="load-carrier" :class="`position-${position}`">
    <div class="header">
      <LoadCarrierHeader :position="position">
        <template #item>
          <slot name="header-item" />
        </template>
        <template #text>
          <slot name="header-text" />
        </template>
      </LoadCarrierHeader>
    </div>
    <div class="content">
      <slot />
    </div>
  </div>
</template>

<script setup lang="ts">
import { defineProps } from 'vue';
import LoadCarrierHeader from './LoadCarrierHeader.vue';

type Position = 'top' | 'left' | 'right';

defineProps<{
  position: Position;
}>();
</script>

<style scoped>
.load-carrier {
  display: flex;
  width: 100%;
  min-height: 400px;
  border: 2px solid #ddd;
  border-radius: 12px;
  overflow: hidden;
  background: white;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
}

.position-top {
  flex-direction: column;
}

.position-left {
  flex-direction: row;
}

.position-right {
  flex-direction: row-reverse;
}

.header {
  flex-shrink: 0;
}

.content {
  flex: 1;
  padding: 2rem;
  background: #fafafa;
  overflow: auto;
}
</style>
