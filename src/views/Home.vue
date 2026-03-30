<script setup>
import Hero from '@/components/Hero.vue';
import Projects from '@/components/Projects.vue';
import About from '@/components/About.vue';
import Experience from '@/components/Experience.vue';
import Contact from '@/components/Contact.vue';

</script>

<template>
  <main class="px-4 sm:px-6 lg:px-8 py-12">
    <Hero />
    <Projects :repositories="repositories" />
    <About />
    <Experience />
    <Contact />
  </main>
</template>

