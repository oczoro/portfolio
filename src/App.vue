<template>
  <div class="w-screen h-screen text-slate-200 overflow-x-hidden relative">
    <Header @set-page="setCurrentPage" :currentPage="current_page" />
    <Content
      @prev-page="prevPage()"
      @next-page="nextPage()"
      :active_page="activePage"
      :transition_dir="transitionDir"
    />
  </div>
</template>

<script setup lang="ts">
import { ref, shallowRef } from 'vue';
import Header from './components/Header.vue';
import Content from './components/Content.vue';
import Landing from './components/Pages/Landing.vue';
import Projects from './components/Pages/Projects.vue';
import About from './components/Pages/About.vue';
import Contact from './components/Pages/Contact.vue';

const pages = [Landing, Projects, About, Contact];

let current_page = ref(0);
let activePage = shallowRef(pages[current_page.value]);
const transitionDir = ref('right');

const setCurrentPage = (page: number) => {
  if (page < current_page.value) {
    transitionDir.value = 'right';
  } else {
    transitionDir.value = 'left';
  }
  current_page.value = page;
  activePage.value = pages[page];
};

const prevPage = () => {
  transitionDir.value = 'right';
  if (current_page.value - 1 < 0) {
    current_page.value = pages.length - 1;
  } else {
    current_page.value--;
  }
  activePage.value = pages[current_page.value];
};

const nextPage = () => {
  transitionDir.value = 'left';
  if (current_page.value + 1 == 4) {
    current_page.value = 0;
  } else {
    current_page.value++;
  }
  activePage.value = pages[current_page.value];
};
</script>

<style>
#app {
  font-family: 'Prompt', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
