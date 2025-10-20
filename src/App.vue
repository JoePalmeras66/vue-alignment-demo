<template>
  <div class="app">
    <h1>Vue Component Alignment Demo</h1>
    <p class="description">
      This demo shows how to dynamically align the header and content components based on position props.
    </p>

    <div class="demo-section">
      <h2>Position: Top</h2>
      <LoadCarrier position="top">
        <template #header-text>
          <h3>Header on Top</h3>
          <p>Header text aligned horizontally</p>
        </template>
        <template #header-item>
          <div class="icon">🔝</div>
        </template>
        <div class="content-demo">
          <h4>Content Area</h4>
          <p>This is the main content area. The header is positioned at the top with a horizontal layout.</p>
          <p>The .header-text is aligned horizontally with space-between.</p>
        </div>
      </LoadCarrier>
    </div>

    <div class="demo-section">
      <h2>Position: Left</h2>
      <LoadCarrier position="left">
        <template #header-text>
          <h3>Header on Left</h3>
          <p>Header text aligned to left</p>
        </template>
        <template #header-item>
          <div class="icon">⬅️</div>
        </template>
        <div class="content-demo">
          <h4>Content Area</h4>
          <p>This is the main content area. The header is positioned on the left with a vertical layout.</p>
          <p>The .header-text is aligned to the left side.</p>
        </div>
      </LoadCarrier>
    </div>

    <div class="demo-section">
      <h2>Position: Right</h2>
      <LoadCarrier position="right">
        <template #header-text>
          <h3>Header on Right</h3>
          <p>Header text aligned to right</p>
        </template>
        <template #header-item>
          <div class="icon">➡️</div>
        </template>
        <div class="content-demo">
          <h4>Content Area</h4>
          <p>This is the main content area. The header is positioned on the right with a vertical layout.</p>
          <p>The .header-text is aligned to the right side.</p>
        </div>
      </LoadCarrier>
    </div>
  </div>
</template>

<script setup lang="ts">
import LoadCarrier from './components/LoadCarrier.vue';
</script>

<style scoped>
.app {
  padding: 20px;
}

h1 {
  color: #333;
  margin-bottom: 10px;
}

.description {
  color: #666;
  margin-bottom: 30px;
  font-size: 1.1rem;
}

.demo-section {
  margin-bottom: 40px;
}

.demo-section h2 {
  color: #1976d2;
  margin-bottom: 15px;
  font-size: 1.5rem;
}

.content-demo {
  line-height: 1.6;
}

.content-demo h4 {
  color: #333;
  margin-bottom: 10px;
}

.content-demo p {
  color: #666;
  margin-bottom: 10px;
}

.icon {
  font-size: 2.5rem;
  display: flex;
  align-items: center;
  justify-content: center;
}
</style>
