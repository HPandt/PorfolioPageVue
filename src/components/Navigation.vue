<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
import { Menu, X } from 'lucide-vue-next'

const isScrolled = ref(false)
const isMobileMenuOpen = ref(false)

const navItems = [
  { label: 'Home', href: '#' },
  { label: 'Projects', href: '#projects' },
  { label: 'About', href: '#about' },
  { label: 'Experience', href: '#experience' },
  { label: 'Contact', href: '#contact' },
]

const handleScroll = () => {
  isScrolled.value = window.scrollY > 50
}

const scrollToSection = (href) => {
  if (href === '#') {
    window.scrollTo({ top: 0, behavior: 'smooth' })
  } else {
    const element = document.querySelector(href)
    if (element) {
      element.scrollIntoView({ behavior: 'smooth' })
    }
  }
  isMobileMenuOpen.value = false
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>

<template>
  <nav
    :class="{
      'bg-black/95 backdrop-blur-sm border-b border-zinc-800': isScrolled,
      'bg-transparent': !isScrolled,
    }"
    class="fixed top-0 left-0 right-0 z-50 transition-all duration-300"
  >
    <div class="max-w-7xl mx-auto px-6 py-4">
      <div class="flex items-center justify-between">
        <button
          @click="scrollToSection('#')"
          class="text-2xl font-bold text-yellow-400 hover:text-yellow-500 transition-colors"
        >
          H . P
        </button>

        <!-- Desktop Navigation -->
        <div class="hidden md:flex items-center gap-8">
          <button
            v-for="item in navItems"
            :key="item.label"
            @click="scrollToSection(item.href)"
            class="text-white hover:text-yellow-400 transition-colors"
          >
            {{ item.label }}
          </button>
        </div>

        <!-- Mobile Menu Button -->
        <button
          @click="isMobileMenuOpen = !isMobileMenuOpen"
          class="md:hidden text-white hover:text-yellow-400 transition-colors"
        >
          <X v-if="isMobileMenuOpen" class="w-6 h-6" />
          <Menu v-else class="w-6 h-6" />
        </button>
      </div>
    </div>
  </nav>

  <!-- Mobile Menu -->
  <div
    v-if="isMobileMenuOpen"
    class="fixed inset-0 z-40 bg-black md:hidden"
    style="top: 64px"
  >
    <div class="flex flex-col items-center justify-center h-full space-y-8">
      <button
        v-for="item in navItems"
        :key="item.label"
        @click="scrollToSection(item.href)"
        class="text-2xl text-white hover:text-yellow-400 transition-colors"
      >
        {{ item.label }}
      </button>
    </div>
  </div>
</template>