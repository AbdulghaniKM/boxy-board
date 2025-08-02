<template>
  <div class="bg-snow">
    <AppHeader />
    <div class="min-h-screen">
      <slot />
    </div>
  </div>
</template>
<script setup lang="ts">
  import AppHeader from '../components/AppHeader.vue';
</script>
