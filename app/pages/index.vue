<template>
  <div class="min-h-screen flex flex-col overflow-x-hidden bg-gradient-to-br from-gray-50 to-gray-100 dark:from-gray-900 dark:to-gray-800">
    <!-- Hero Section with Dramatic Typography -->
    <section class="relative h-screen flex items-center justify-center px-4 sm:px-6 lg:px-8 overflow-hidden">
      <!-- Animated gradient background -->
      <div class="fixed inset-0 -z-10">
        <div class="absolute inset-0 bg-[radial-gradient(ellipse_at_center,_var(--tw-gradient-stops))] from-blue-100/30 via-transparent to-transparent dark:from-blue-900/10"></div>
        <div class="absolute inset-0 bg-[radial-gradient(ellipse_at_top_right,_var(--tw-gradient-stops))] from-purple-100/30 via-transparent to-transparent dark:from-purple-900/10"></div>
        <div class="absolute inset-0 bg-[radial-gradient(ellipse_at_bottom_left,_var(--tw-gradient-stops))] from-pink-100/30 via-transparent to-transparent dark:from-pink-900/10"></div>
      </div>
      <!-- Background Text -->
      <div class="absolute inset-0 flex items-center justify-center pointer-events-none">
        <div class="hero-text-container w-full">
          <h1 class="hero-text text-[15vw] md:text-[20vw] font-black leading-[0.8] tracking-tight text-center opacity-5 dark:opacity-5">
            <span class="block">MINIMAL</span>
            <span class="block">DESIGN</span>
            <span class="block">ESSENCE</span>
          </h1>
        </div>
      </div>
      
      <!-- Main Content -->
      <div class="glass-panel relative z-10 text-center max-w-6xl mx-auto w-full backdrop-blur-xl">
        <div class="hero-content opacity-100 transition-opacity duration-1000">
          <h2 class="text-xl md:text-2xl font-light tracking-widest mb-6 text-gray-600 dark:text-gray-400">
            WELCOME TO THE NEW ERA
          </h2>
          <h1 class="text-6xl md:text-8xl lg:text-9xl font-black tracking-tight leading-none mb-8">
            <span class="block">MINIMAL</span>
            <span class="block text-transparent bg-clip-text bg-gradient-to-r from-gray-900 to-gray-600 dark:from-white dark:to-gray-300">
              DESIGN
            </span>
            <span class="block">ESSENCE</span>
          </h1>
          <p class="text-lg md:text-xl text-gray-600 dark:text-gray-300 max-w-2xl mx-auto mb-12">
            Where simplicity meets sophistication in digital craftsmanship.
          </p>
          <div class="flex flex-col sm:flex-row justify-center gap-6 mt-12">
            <NuxtLink 
              to="/work" 
              class="glass-button text-white font-medium hover:shadow-xl hover:scale-105"
            >
              <span class="glass-text font-semibold">EXPLORE WORK</span>
            </NuxtLink>
            <NuxtLink 
              to="/contact" 
              class="glass-button bg-gradient-to-r from-blue-500/20 to-purple-500/20 border border-white/20 text-white font-medium hover:shadow-xl hover:scale-105"
            >
              <span class="glass-text font-semibold">START PROJECT</span>
            </NuxtLink>
          </div>
        </div>
      </div>
      
      <!-- Scroll Indicator -->
      <div class="glass absolute bottom-8 left-1/2 transform -translate-x-1/2 animate-bounce p-3 rounded-full">
        <div class="flex flex-col items-center">
          <span class="text-xs uppercase tracking-widest mb-1 text-white/80">SCROLL</span>
          <svg class="w-4 h-8 text-white/80" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M19 14l-7 7m0 0l-7-7m7 7V3"></path>
          </svg>
        </div>
      </div>
    </section>
    
    <!-- Features Section -->
    <section class="py-20 bg-gray-50 dark:bg-gray-900">
      <div class="container mx-auto px-4 sm:px-6 lg:px-8">
        <div class="max-w-3xl mx-auto text-center mb-16">
          <h2 class="text-3xl md:text-4xl font-bold mb-6">Our Approach</h2>
          <p class="text-gray-600 dark:text-gray-300">
            We believe in simplicity, clarity, and purpose in everything we create.
          </p>
        </div>
        
        <div class="grid md:grid-cols-3 gap-8">
          <div class="glass p-8 rounded-2xl hover:shadow-xl transition-shadow">
            <div class="w-12 h-12 rounded-full bg-black dark:bg-white flex items-center justify-center mb-6 mx-auto">
              <svg class="w-6 h-6 text-white dark:text-black" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 10V3L4 14h7v7l9-11h-7z"></path>
              </svg>
            </div>
            <h3 class="text-xl font-semibold mb-3">Lightning Fast</h3>
            <p class="text-gray-600 dark:text-gray-300">
              Optimized for performance to deliver the fastest experience possible.
            </p>
          </div>
          
          <div class="glass p-8 rounded-2xl hover:shadow-xl transition-shadow">
            <div class="w-12 h-12 rounded-full bg-black dark:bg-white flex items-center justify-center mb-6 mx-auto">
              <svg class="w-6 h-6 text-white dark:text-black" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 15v2m-6 4h12a2 2 0 002-2v-6a2 2 0 00-2-2H6a2 2 0 00-2 2v6a2 2 0 002 2zm10-10V7a4 4 0 00-8 0v4h8z"></path>
              </svg>
            </div>
            <h3 class="text-xl font-semibold mb-3">Secure by Design</h3>
            <p class="text-gray-600 dark:text-gray-300">
              Built with security in mind from the ground up.
            </p>
          </div>
          
          <div class="glass p-8 rounded-2xl hover:shadow-xl transition-shadow">
            <div class="w-12 h-12 rounded-full bg-black dark:bg-white flex items-center justify-center mb-6 mx-auto">
              <svg class="w-6 h-6 text-white dark:text-black" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 5a1 1 0 011-1h14a1 1 0 011 1v2a1 1 0 01-1 1H5a1 1 0 01-1-1V5zM4 13a1 1 0 011-1h6a1 1 0 011 1v6a1 1 0 01-1 1H5a1 1 0 01-1-1v-6zM16 13a1 1 0 011-1h2a1 1 0 011 1v6a1 1 0 01-1 1h-2a1 1 0 01-1-1v-6z"></path>
              </svg>
            </div>
            <h3 class="text-xl font-semibold mb-3">Responsive</h3>
            <p class="text-gray-600 dark:text-gray-300">
              Looks great on any device, from mobile to desktop.
            </p>
          </div>
        </div>
      </div>
    </section>
    
    <!-- CTA Section -->
    <section class="py-20 bg-black dark:bg-white text-white dark:text-black">
      <div class="container mx-auto px-4 sm:px-6 lg:px-8 text-center">
        <h2 class="text-3xl md:text-4xl font-bold mb-6">Ready to get started?</h2>
        <p class="text-xl text-gray-300 dark:text-gray-700 mb-8 max-w-2xl mx-auto">
          Let's create something amazing together.
        </p>
        <NuxtLink 
          to="/contact" 
          class="inline-block px-8 py-4 bg-white dark:bg-black text-black dark:text-white font-medium rounded-full hover:opacity-90 transition-opacity"
        >
          Contact Us
        </NuxtLink>
      </div>
    </section>
  </div>
</template>

<script setup>
useHead({
  title: 'Home - Minimal & Modern Digital Experience',
  meta: [
    { name: 'description', content: 'Crafting elegant digital experiences with a focus on simplicity and performance.' }
  ]
})
</script>

<style scoped>
.glass {
  background: rgba(255, 255, 255, 0.7);
  backdrop-filter: blur(10px);
  -webkit-backdrop-filter: blur(10px);
  border: 1px solid rgba(255, 255, 255, 0.2);
}

.dark .glass {
  background: rgba(0, 0, 0, 0.7);
  border-color: rgba(255, 255, 255, 0.1);
}

/* Hero Text Styles */
.hero-text {
  font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
  letter-spacing: -0.03em;
  line-height: 0.8;
  font-weight: 900;
  text-transform: uppercase;
  -webkit-text-stroke: 1px rgba(0, 0, 0, 0.1);
  color: transparent;
}

.dark .hero-text {
  -webkit-text-stroke: 1px rgba(255, 255, 255, 0.1);
}

/* Animation for hero section */
.hero-content {
  animation: fadeInUp 1.2s cubic-bezier(0.16, 1, 0.3, 1) forwards;
  opacity: 0;
  transform: translateY(20px);
}

@keyframes fadeInUp {
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

/* Scroll behavior */
html {
  scroll-behavior: smooth;
}

/* Responsive adjustments */
@media (max-width: 768px) {
  .hero-text {
    font-size: 20vw;
    line-height: 0.85;
  }
  
  .hero-content h1 {
    font-size: 3.5rem;
  }
}

/* Scroll-based animations */
@keyframes fadeOutUp {
  from {
    opacity: 1;
    transform: translateY(0);
  }
  to {
    opacity: 0;
    transform: translateY(-20px);
  }
}

.scrolled .hero-content {
  animation: fadeOutUp 0.6s cubic-bezier(0.16, 1, 0.3, 1) forwards;
}
</style>

<script setup>
import { onMounted, onUnmounted } from 'vue';

const handleScroll = () => {
  const heroSection = document.querySelector('section:first-of-type');
  if (window.scrollY > 50) {
    heroSection.classList.add('scrolled');
  } else {
    heroSection.classList.remove('scrolled');
  }
};

onMounted(() => {
  window.addEventListener('scroll', handleScroll);
  
  // Preload fonts for better performance
  if (typeof window !== 'undefined') {
    const link = document.createElement('link');
    link.href = 'https://fonts.googleapis.com/css2?family=Inter:wght@900&display=swap';
    link.rel = 'stylesheet';
    document.head.appendChild(link);
  }
});

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll);
});
</script>
