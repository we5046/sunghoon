<template>
  <div class="app-layout">
    <Sidebar />
    <main class="app-content">
      <RouterView />
    </main>
  </div>
</template>

<script setup>
import Sidebar from '@/components/common/Sidebar.vue';
</script>

<style scoped>
.app-layout {
  display: flex;
  min-height: 100vh;
}

.app-content {
  flex: 1;
  padding: 24px;
  background-color: #f8f9fa;
}
</style>
