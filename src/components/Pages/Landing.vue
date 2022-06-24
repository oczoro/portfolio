<template>
  <div class="self-center h-fit mx-2">
    <div class="card py-10 px-8 md:p-36 flex flex-col text-center">
      <h2 class="text-5xl md:text-6xl">Kevin Orozco</h2>
      <h3 class="text-3xl md:text-4xl">Software Developer</h3>
      <ul
        class="mt-4 inline-flex flex-wrap gap-4 justify-center text-lg ease-in duration-200"
      >
        <li>Java</li>
        <li>Python</li>
        <li>Javascript</li>
        <li>Android</li>
        <li>Node.js</li>
        <li>Vue.js</li>
        <li>Tailwind CSS</li>
        <li>MongoDB</li>
      </ul>
      <div
        class="flex mt-6 md:mt-14 justify-center items-center gap-6 md:gap-10"
      >
        <button
          @click="$emit('nextPage')"
          class="button-sm md:button w-fit text-xl md:text-2xl hover:-translate-y-1"
        >
          My Projects
          <i class="fa-solid fa-arrow-right"></i>
        </button>
      </div>
      <!-- <div
        class="flex mt-6 md:mt-14 justify-center items-center gap-6 md:gap-10"
      >
        <a
          href="./resume.pdf"
          target="_blank"
          class="button-sm md:button w-fit text-xl md:text-2xl hover:-translate-y-1"
        >
          Resume
        </a>
        <a
          href="https://github.com/oczoro"
          target="_blank"
          class="button-blue-sm md:button-blue w-fit text-xl md:text-2xl hover:-translate-y-1"
        >
          GitHub
        </a>
      </div> -->
    </div>
  </div>
</template>

<script setup lang="ts"></script>

<style scoped></style>
