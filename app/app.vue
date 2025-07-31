<script setup lang="ts">
import { Toaster } from 'vue-sonner'
import * as locales from '@nuxt/ui/locale'
import { onMounted, ref } from 'vue'
import { useHead } from '#imports'
import ScrollProgress from '~/components/ScrollProgress.vue'
import BackToTop from '~/components/BackToTop.vue'

const { locale } = useI18n()
const isDark = ref(false)

// Set initial theme
onMounted(() => {
  if (typeof window !== 'undefined') {
    if (localStorage.theme === 'dark' || (!('theme' in localStorage) && window.matchMedia('(prefers-color-scheme: dark)').matches)) {
      document.documentElement.classList.add('dark')
      isDark.value = true
    } else {
      document.documentElement.classList.remove('dark')
      isDark.value = false
    }
  }
})

const toggleTheme = () => {
  if (typeof window !== 'undefined') {
    if (isDark.value) {
      document.documentElement.classList.remove('dark')
      localStorage.theme = 'light'
    } else {
      document.documentElement.classList.add('dark')
      localStorage.theme = 'dark'
    }
    isDark.value = !isDark.value
  }
}

// Set up head with theme color
useHead({
  htmlAttrs: {
    class: 'h-full',
  },
  body: {
    class: 'min-h-screen bg-gradient-to-br from-gray-50 to-gray-100 dark:from-gray-900 dark:to-gray-800 text-gray-900 dark:text-white transition-colors duration-300 overflow-x-hidden',
  },
  meta: [
    { name: 'theme-color', content: computed(() => isDark.value ? '#000000' : '#ffffff') },
  ],
})
</script>

<template>
  <Html
    :lang="locale"
    class="font-geist text-[var(--ui-text)] transition-colors duration-300 selection:bg-black/10 dark:selection:bg-white/20 selection:text-current"
  >
    <Body class="antialiased bg-white dark:bg-black transition-colors duration-300">
      <ScrollProgress />
      <BackToTop />
      <LayoutScrollToTop />
      
      <div class="min-h-screen flex flex-col">
        <!-- Header -->
        <header class="fixed top-0 left-0 right-0 z-50 glass-header border-b border-white/10 dark:border-gray-800/30">
          <div class="container mx-auto px-4 sm:px-6">
            <div class="flex items-center justify-between h-16">
              <!-- Logo -->
              <NuxtLink to="/" class="text-xl font-bold tracking-tight">
                <span class="text-black dark:text-white">CASTLE</span>
              </NuxtLink>
              
              <!-- Navigation -->
              <nav class="hidden md:flex items-center space-x-8">
                <NuxtLink to="/" class="text-sm font-medium hover:text-gray-900 dark:hover:text-white transition-colors">
                  Home
                </NuxtLink>
                <NuxtLink to="/about" class="text-sm font-medium hover:text-gray-900 dark:hover:text-white transition-colors">
                  About
                </NuxtLink>
                <NuxtLink to="/work" class="text-sm font-medium hover:text-gray-900 dark:hover:text-white transition-colors">
                  Work
                </NuxtLink>
                <NuxtLink to="/contact" class="text-sm font-medium hover:text-gray-900 dark:hover:text-white transition-colors">
                  Contact
                </NuxtLink>
              </nav>
              
              <!-- Theme Toggle -->
              <button
                @click="toggleTheme"
                class="p-2 rounded-full hover:bg-gray-100 dark:hover:bg-gray-800 transition-colors"
                :aria-label="isDark ? 'Switch to light mode' : 'Switch to dark mode'"
              >
                <svg v-if="isDark" class="w-5 h-5 text-yellow-300" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 3v1m0 16v1m9-9h-1M4 12H3m15.364 6.364l-.707-.707M6.343 6.343l-.707-.707m12.728 0l-.707.707M6.343 17.657l-.707.707M16 12a4 4 0 11-8 0 4 4 0 018 0z" />
                </svg>
                <svg v-else class="w-5 h-5 text-gray-700 dark:text-gray-300" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M20.354 15.354A9 9 0 018.646 3.646 9.003 9.003 0 0012 21a9.003 9.003 0 008.354-5.646z" />
                </svg>
              </button>
            </div>
          </div>
        </header>
        
        <!-- Main Content -->
        <main class="pt-16 relative">
          <!-- Animated background elements -->
          <div class="fixed inset-0 -z-10 overflow-hidden">
            <!-- Animated gradient circles -->
            <div class="absolute -top-64 -right-64 w-[600px] h-[600px] rounded-full bg-blue-500/10 dark:bg-blue-500/5 blur-3xl animate-float"></div>
            <div class="absolute -bottom-64 -left-64 w-[800px] h-[800px] rounded-full bg-purple-500/10 dark:bg-purple-500/5 blur-3xl animate-float animation-delay-2000"></div>
            <div class="absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 w-[1000px] h-[1000px] rounded-full bg-pink-500/5 dark:bg-pink-500/3 blur-3xl animate-pulse animation-delay-1000"></div>
          </div>
          <NuxtLayout>
            <UApp :locale="locales[locale]">
              <NuxtPage />
            </UApp>
          </NuxtLayout>
        </main>
        
        <!-- Footer -->
        <footer class="border-t border-gray-200 dark:border-gray-800 py-8">
          <div class="container mx-auto px-4 sm:px-6">
            <div class="flex flex-col md:flex-row justify-between items-center">
              <div class="text-sm text-gray-600 dark:text-gray-400">
                {{ new Date().getFullYear() }} Castle. All rights reserved.
              </div>
            </div>
          </div>
        </footer>
      </div>
      
      <!-- Toaster -->
      <Toaster position="top-center" richColors closeButton />
      
      <!-- Scroll to Top -->
      <LayoutScrollToTop />
      
      <!-- Background Pattern -->
      <div class="fixed inset-0 -z-10 opacity-10 dark:opacity-5">
        <div class="absolute inset-0 bg-grid-pattern"></div>
      </div>
    </Body>
  </Html>
</template>

<style>
.bg-grid-pattern {
  background-image: url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 32 32' width='32' height='32' fill='none' stroke='%23000000'%3e%3cpath d='M0 .5H31.5V32'/%3e%3c/svg%3e");
}

.dark .bg-grid-pattern {
  background-image: url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 32 32' width='32' height='32' fill='none' stroke='%23ffffff'%3e%3cpath d='M0 .5H31.5V32'/%3e%3c/svg%3e");
}
</style>
