<script setup>
import { useAuthStore } from '@/stores/auth';

const authStore = useAuthStore();
</script>

<template>
  <MyPageContent :user="authStore.currentUser" />
</template>
