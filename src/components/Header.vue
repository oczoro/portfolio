<template>
  <header
    class="flex py-2 px-2 md:px-6 items-center gap-4 md:justify-between md:gap-0"
  >
    <div
      @click="$emit('set-page', 0)"
      class="logo-card z-50 flex items-center text-2xl select-none cursor-pointer md:text-xl"
    >
      <span
        class="inline-block align-middle"
        :class="currentPage == 0 ? 'text-red-500' : ''"
        >OCZORO</span
      >
    </div>

    <div
      class="toggle-nav absolute top-6 right-6 z-50 text-3xl md:hidden"
      @click="menu_toggled = !menu_toggled"
    >
      <span class="hidden" aria-readonly="true">Menu</span>
      <i class="fa-solid" :class="menu_toggled ? 'fa-xmark' : 'fa-bars'"></i>
    </div>

    <nav
      class="absolute top-0 left-1/3 z-20 bottom-0 right-0 bg-neutral-900 bg-opacity-75 backdrop-blur-sm transition-transform ease-out md:relative md:translate-x-0 md:inset-0 md:bg-transparent uppercase"
      :class="menu_toggled ? '' : 'translate-x-full '"
    >
      <ul
        class="navbar flex flex-col justify-center pt-36 px-10 gap-8 text-xl md:flex-row md:gap-10 md:text-base md:p-0"
      >
        <li
          @click="$emit('set-page', 1)"
          class="py-4 px-10 cursor-pointer select-none"
          :class="currentPage == 1 ? 'md:link-active' : 'md:link'"
        >
          <span>Projects</span>
        </li>
        <li
          @click="$emit('set-page', 2)"
          class="py-4 px-10 cursor-pointer select-none"
          :class="currentPage == 2 ? 'md:link-active' : 'md:link'"
        >
          <span>About</span>
        </li>
        <li
          @click="$emit('set-page', 3)"
          class="py-4 px-10 cursor-pointer select-none"
          :class="currentPage == 3 ? 'md:link-active' : 'md:link'"
        >
          <span>Contact</span>
        </li>
      </ul>
    </nav>
  </header>
</template>

<script setup lang="ts">
import { ref } from 'vue';
const menu_toggled = ref(false);

const props = defineProps({ currentPage: Number });
</script>

<style scoped></style>
