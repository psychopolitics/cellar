<template>
  <div class="min-h-screen flex items-center justify-center text-center px-4">
    <div class="max-w-2xl mx-auto">
      <h1 class="text-9xl font-black text-gray-900 dark:text-white mb-4">404</h1>
      <h2 class="text-3xl md:text-5xl font-bold mb-6">Page Not Found</h2>
      <p class="text-lg text-gray-600 dark:text-gray-300 mb-8">
        The page you're looking for doesn't exist or has been moved.
      </p>
      <NuxtLink 
        to="/" 
        class="inline-flex items-center px-6 py-3 border border-transparent text-base font-medium rounded-full text-white bg-black dark:bg-white dark:text-black hover:opacity-90 transition-opacity"
      >
        <span>Back to Home</span>
        <svg class="ml-2 -mr-1 w-5 h-5" fill="currentColor" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg">
          <path fill-rule="evenodd" d="M10.293 3.293a1 1 0 011.414 0l6 6a1 1 0 010 1.414l-6 6a1 1 0 01-1.414-1.414L14.586 11H3a1 1 0 110-2h11.586l-4.293-4.293a1 1 0 010-1.414z" clip-rule="evenodd"></path>
        </svg>
      </NuxtLink>
    </div>
  </div>
</template>

<script setup>
useHead({
  title: '404 - Page Not Found',
  meta: [
    { name: 'robots', content: 'noindex' }
  ]
});
</script>

<style scoped>
h1 {
  font-size: clamp(6rem, 25vw, 12rem);
  line-height: 1;
  margin-bottom: 1rem;
  background: linear-gradient(135deg, #000 0%, #333 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  text-fill-color: transparent;
}

dark h1 {
  background: linear-gradient(135deg, #fff 0%, #ccc 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  text-fill-color: transparent;
}
</style>
