<template>
  <button
    @click="toggleTheme"
    class="theme-toggle relative flex items-center justify-center w-10 h-10 rounded-full transition-colors duration-200 hover:bg-gray-200 dark:hover:bg-gray-800 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-gray-500 dark:focus:ring-gray-400"
    aria-label="Toggle theme"
  >
    <span class="sr-only">Toggle theme</span>
    <svg
      v-if="isDark"
      xmlns="http://www.w3.org/2000/svg"
      class="w-5 h-5 text-yellow-300"
      viewBox="0 0 20 20"
      fill="currentColor"
    >
      <path
        fill-rule="evenodd"
        d="M10 2a1 1 0 011 1v1a1 1 0 11-2 0V3a1 1 0 011-1zm4 8a4 4 0 11-8 0 4 4 0 018 0zm-.464 4.95l.707.707a1 1 0 001.414-1.414l-.707-.707a1 1 0 00-1.414 1.414zm2.12-10.607a1 1 0 010 1.414l-.706.707a1 1 0 11-1.414-1.414l.707-.707a1 1 0 011.414 0zM17 11a1 1 0 100-2h-1a1 1 0 100 2h1zm-7 4a1 1 0 011 1v1a1 1 0 11-2 0v-1a1 1 0 011-1zM5.05 6.464A1 1 0 106.465 5.05l-.708-.707a1 1 0 00-1.414 1.414l.707.707zm1.414 8.486l-.707.707a1 1 0 01-1.414-1.414l.707-.707a1 1 0 011.414 1.414zM4 11a1 1 0 100-2H3a1 1 0 000 2h1z"
        clip-rule="evenodd"
      />
    </svg>
    <svg
      v-else
      xmlns="http://www.w3.org/2000/svg"
      class="w-5 h-5 text-gray-700"
      viewBox="0 0 20 20"
      fill="currentColor"
    >
      <path
        d="M17.293 13.293A8 8 0 016.707 2.707a8.001 8.001 0 1010.586 10.586z"
      />
    </svg>
  </button>
</template>

<script setup>
import { ref, onMounted } from 'vue';

const isDark = ref(false);

const checkDarkMode = () => {
  if (typeof window !== 'undefined') {
    isDark.value = document.documentElement.classList.contains('dark');
  }
};

const toggleTheme = () => {
  if (typeof window !== 'undefined') {
    if (isDark.value) {
      document.documentElement.classList.remove('dark');
      localStorage.theme = 'light';
    } else {
      document.documentElement.classList.add('dark');
      localStorage.theme = 'dark';
    }
    isDark.value = !isDark.value;
  }
};

onMounted(() => {
  if (typeof window !== 'undefined') {
    // Check for saved theme preference or use system preference
    if (localStorage.theme === 'dark' || (!('theme' in localStorage) && window.matchMedia('(prefers-color-scheme: dark)').matches)) {
      document.documentElement.classList.add('dark');
      isDark.value = true;
    } else {
      document.documentElement.classList.remove('dark');
      isDark.value = false;
    }
    
    // Watch for system theme changes
    const darkModeMediaQuery = window.matchMedia('(prefers-color-scheme: dark)');
    darkModeMediaQuery.addEventListener('change', (e) => {
      if (!('theme' in localStorage)) {
        if (e.matches) {
          document.documentElement.classList.add('dark');
          isDark.value = true;
        } else {
          document.documentElement.classList.remove('dark');
          isDark.value = false;
        }
      }
    });
  }
});
</script>

<style scoped>
.theme-toggle {
  transition: background-color 0.2s ease-in-out, transform 0.2s ease-in-out;
}

.theme-toggle:active {
  transform: scale(0.95);
}
</style>
