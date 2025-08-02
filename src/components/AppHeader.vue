<template>
  <div class="p-6 px-28">
    <div class="bg-rasberry flex h-30 items-center justify-between rounded-xl px-8">
      <div class="flex items-center gap-4">
        <div class="flex items-center justify-center gap-2">
          <BoxIcon class="h-16 w-16" />
          <p class="text-snow font-Hand text-4xl">BB</p>
        </div>
      </div>
      <div class="flex items-center justify-center">
        <MenuIcon class="h-16 w-16 hover:cursor-pointer" @click="toggleMenu" />
      </div>
    </div>
    <div
      v-if="showMenuModal"
      class="transition-all transition-discrete duration-300"
      :class="showMenuModal ? 'block' : 'opacity-0'"
    >
      <div
        class="bg-rasberry -mt-2 flex h-30 items-center justify-center rounded-xl rounded-t-none px-8"
      >
        <div class="flex justify-center">
          <ul class="text-snow flex flex-row items-center justify-center gap-12">
            <li
              v-for="(item, index) in navLinks"
              :key="index"
              class="font-Hand text-2xl"
              :class="router.currentRoute.value.fullPath == item.link ? 'underline' : ''"
            >
              {{ item.name }}
            </li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
  import { ref } from 'vue';
  import { useRouter } from 'vue-router';
  import BoxIcon from './icons/BoxIcon.vue';
  import MenuIcon from './icons/MenuIcon.vue';
  const router = useRouter();
  const showMenuModal = ref(false);
  const toggleMenu = () => {
    showMenuModal.value = !showMenuModal.value;
  };
  const navLinks = [
    {
      name: 'Home',
      link: '/',
    },
    {
      name: 'About Us',
      link: '/about',
    },
    {
      name: 'Pricing',
      link: '/price',
    },
  ];
</script>
