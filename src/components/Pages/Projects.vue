<template>
  <div class="project-container mt-[15vh] h-fit text-center">
    <h2 class="text-4xl mb-8 z-50">Projects</h2>
    <div
      class="projects flex flex-wrap w-[70%] mb-20 mx-auto justify-evenly gap-16"
    >
      <div
        class="project-card flex-none flex flex-wrap p-6 max-w-sm"
        v-for="(project, index) in project_list"
        :key="index"
      >
        <div
          class="flex flex-col p-6 w-80 h-80 space-y-4 justify-between text-center"
        >
          <div class="flex flex-col">
            <div class="name text-3xl font-medium tracking-wider">
              {{ project.name }}
            </div>
            <div class="description mt-2 text-gray-300">
              {{ project.description }}
            </div>
          </div>
          <div class="flex flex-col">
            <div class="project-buttons flex justify-center gap-2 text-center">
              <a
                :href="project.github_url"
                target="_blank"
                class="border-2 w-20 py-1 px-2 rounded-lg hover:border-purple-400 hover:text-purple-400 active:bg-purple-500 active:text-inherit duration-300 delay-75 ease-in-out"
              >
                Source
              </a>
              <!-- <button
              class="border-2 w-20 py-1 px-2 rounded-lg hover:border-blue-400 hover:text-blue-400 active:bg-blue-500 active:text-inherit duration-300 delay-75 ease-in-out"
            >
              Demo
            </button> -->
              <a
                :href="project.info_url"
                target="_blank"
                class="border-2 w-20 py-1 px-2 rounded-lg hover:border-green-400 hover:text-green-400 active:bg-green-500 active:text-inherit duration-300 delay-75 ease-in-out"
              >
                More
              </a>
            </div>
            <div class="technologies pt-4 flex flex-wrap justify-center gap-2">
              <div
                class="py-1 px-2 rounded-sm text-zinc-800"
                :class="technology == '?' ? 'NO-TECH' : technology"
                v-for="(technology, index) in project.technologies"
                :key="index"
              >
                {{ technology }}
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';

const project_list = ref([
  {
    name: 'Star Calendar',
    description:
      'Web App that lets users track the progress of their goals using a calendar.',
    technologies: ['VUE', 'FIREBASE', 'JAVASCRIPT', 'NODE'],
    github_url: 'https://github.com/oczoro/star-calendar',
    info_url: 'https://star-calendar.herokuapp.com/',
    thumbnail: '',
    images: [],
  },
  {
    name: 'Echo Wallet',
    description:
      'Automatic investment portfolio manager that picks stocks based on social media trends.',
    technologies: ['VUE', 'JAVASCRIPT', 'JAVA', 'PYTHON', 'SPRINGBOOT'],
    github_url: 'https://github.com/Pancax/EchoWallet',
    info_url: 'https://devpost.com/software/echo-wallet',
    thumbnail: '',
    images: [],
  },
  {
    name: 'Common Cents',
    description:
      'Android app that helps users save for an emergency fund by rounding up everyday purchases.',
    technologies: ['JAVASCRIPT', 'JAVA', 'ANDROID'],
    github_url: 'https://github.com/Pancax/COCommonCents',
    info_url: 'https://devpost.com/software/common-cents-8026sj',
    thumbnail: '',
    images: [],
  },
  {
    name: 'BAC-Home',
    description:
      'Android app that measures blood alcohol content of a person and provides a free uber if they are not fit to drive.',
    technologies: ['TWILIO', 'JAVA', 'ANDROID'],
    github_url: 'https://github.com/Pancax/BAC-Home',
    info_url: 'https://devpost.com/software/bac-home',
    thumbnail: '',
    images: [],
  },
  // {
  //   name: 'Bunn Co.',
  //   description: 'An ecommerce store that sells discounted digital items.',
  //   technologies: ['VUE', 'JAVASCRIPT', 'JAVA', 'POSTGRES', 'SPRINGBOOT'],
  //   thumbnail: '',
  //   images: [],
  // },
]);
</script>

<style scoped>
@media (min-width: 768px) {
  .project-container {
    margin-top: 14vh;
  }
}
@media (min-width: 1274px) {
  .project-container {
    margin-top: 16vh;
  }
}

.inner-project-card {
  padding: theme('padding.8');
  border-radius: 10px;
  border-width: 0.5rem;
  border-color: #3f3f46;
}
</style>
