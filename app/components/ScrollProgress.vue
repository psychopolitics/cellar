<template>
  <div 
    class="fixed top-0 left-0 h-0.5 bg-black dark:bg-white z-50 transition-opacity duration-300"
    :class="{ 'opacity-0': !isScrolled }"
    :style="{ width: scrollProgress + '%' }"
  />
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue';

const scrollProgress = ref(0);
const isScrolled = ref(false);

const handleScroll = () => {
  const winScroll = document.body.scrollTop || document.documentElement.scrollTop;
  const height = document.documentElement.scrollHeight - document.documentElement.clientHeight;
  const scrolled = (winScroll / height) * 100;
  scrollProgress.value = scrolled;
  isScrolled.value = winScroll > 10;
};

onMounted(() => {
  window.addEventListener('scroll', handleScroll);
  handleScroll();
});

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll);
});
</script>
