<template>
  <Transition name="fade">
    <button
      v-if="isVisible"
      aria-label="Back to top"
      class="fixed bottom-8 right-8 z-40 p-3 rounded-full bg-black dark:bg-white text-white dark:text-black shadow-lg hover:opacity-90 transition-all duration-300 transform hover:scale-110 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-black dark:focus:ring-white"
      @click="scrollToTop"
    >
      <svg
        class="w-6 h-6"
        fill="none"
        stroke="currentColor"
        viewBox="0 0 24 24"
        xmlns="http://www.w3.org/2000/svg"
      >
        <path
          stroke-linecap="round"
          stroke-linejoin="round"
          stroke-width="2"
          d="M5 11l7-7 7 7M12 18V4"
        />
      </svg>
    </button>
  </Transition>
</template>

<script setup>
import { computed } from 'vue'
import { useWindowScroll } from '@vueuse/core'

const { y } = useWindowScroll()
const isVisible = computed(() => y.value > 300)

const scrollToTop = () => {
  window.scrollTo({
    top: 0,
    behavior: 'smooth',
  })
}
</script> 