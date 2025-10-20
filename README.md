# Vue Component Alignment Demo

This demo shows how to dynamically align Vue components based on position props (top, left, right).

## Features

- **LoadCarrier Component**: A flexible container that positions its header relative to content
- **LoadCarrierHeader Component**: A header component that adjusts its internal layout based on position
- **TypeScript Support**: Fully typed with TypeScript
- **Three Position Modes**:
  - `top`: Header above content (horizontal layout)
  - `left`: Header on left side (vertical layout)
  - `right`: Header on right side (vertical layout)

## How to Import into CodeSandbox

1. Go to [CodeSandbox](https://codesandbox.io/)
2. Click "Create Sandbox"
3. Select "Import from GitHub"
4. Or simply upload the project files

## Local Development

```bash
npm install
npm run dev
```

## Project Structure

```
src/
├── components/
│   ├── LoadCarrier.vue       # Main container component
│   └── LoadCarrierHeader.vue # Header component with dynamic alignment
├── App.vue                    # Demo application
├── main.ts                    # Application entry point
└── style.css                  # Global styles
```

## Usage Example

```vue
<template>
  <LoadCarrier position="top">
    <template #header-text>
      <h3>My Header</h3>
    </template>
    <template #header-item>
      <div>Icon</div>
    </template>
    <div>Your content here</div>
  </LoadCarrier>
</template>

<script setup lang="ts">
import LoadCarrier from './components/LoadCarrier.vue';
</script>
```

## How It Works

The solution uses dynamic class binding to control flexbox direction and alignment:

- **LoadCarrier**: Uses `position-${position}` classes to control flex-direction
- **LoadCarrierHeader**: Uses `align-${position}` classes to control internal alignment

The position prop automatically cascades from LoadCarrier to LoadCarrierHeader, ensuring consistent alignment throughout.
