<template>
  <div
    class="content-container absolute top-0 left-0 right-0 h-screen w-screen"
  >
    <div
      @click="$emit('prev-page')"
      class="fixed left-4 top-1/2 text-5xl select-none cursor-pointer z-10 opacity-70 hover:-translate-y-1 hover:opacity-90 duration-100 ease-in-out active:scale-90 active:brightness-90"
    >
      <i class="fa-solid fa-arrow-left"></i>
    </div>
    <div
      class="flex absolute left-0 right-0 top-0 bottom-0 justify-center align-middle"
    >
      <Transition :name="`slide-${transition_dir}`" mode="out-in">
        <component :is="active_page" @nextPage="$emit('next-page')"></component>
      </Transition>
    </div>
    <div
      @click="$emit('next-page')"
      class="fixed right-4 top-1/2 text-5xl select-none cursor-pointer z-10 opacity-70 hover:-translate-y-1 hover:opacity-90 duration-100 ease-in-out active:scale-90 active:brightness-90"
    >
      <i class="fa-solid fa-arrow-right"></i>
    </div>
  </div>
</template>

<script setup lang="ts">
const props = defineProps({ active_page: Object, transition_dir: String });
</script>

<style scoped>
.slide-left-enter-active,
.slide-left-leave-active {
  transition: all 0.25s ease-out;
}

.slide-left-enter-from {
  opacity: 0;
  transform: translateX(30px);
}

.slide-left-leave-to {
  opacity: 0;
  transform: translateX(-30px);
}

.slide-right-enter-active,
.slide-right-leave-active {
  transition: all 0.25s ease-out;
}

.slide-right-enter-from {
  opacity: 0;
  transform: translateX(-30px);
}

.slide-right-leave-to {
  opacity: 0;
  transform: translateX(30px);
}
</style>
