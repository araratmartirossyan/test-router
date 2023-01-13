<template>
  <div class="page">
    <div class="page-content">
      <slot></slot>
    </div>
  </div>
</template>

<style>
.page-content {
  flex-grow: 1;
  overflow-x: hidden;
  overflow-y: auto;
  z-index: 104;
  padding: 8px;
}

.page {
  font-family: monospace;
  box-sizing: border-box;
  bottom: 0;
  display: flex;
  flex-direction: column;
  left: 0;
  padding: 0;
  padding: env(safe-area-inset-top, 0) env(safe-area-inset-right, 0)
    env(safe-area-inset-bottom, 0) env(safe-area-inset-left, 0);
  position: absolute;
  right: 0;
  top: 0;
}
</style>
