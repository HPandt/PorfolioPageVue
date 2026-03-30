<script setup>
import { Github, Mail, Linkedin, ArrowDown } from 'lucide-vue-next';

</script>

<template>

    <section className="min-h-screen flex flex-col md:flex-row items-center justify-center relative bg-black text-white px-6">
      <div className="max-w-4xl w-full">
        <div className="space-y-6">
          <div className="inline-block">
            <span className="text-yellow-400 text-lg font-semibold tracking-wider">Hello, I'm</span>
          </div>
          <h1 className="text-7xl md:text-8xl lg:text-9xl font-bold tracking-tight">
            Hunter <span className="text-yellow-400">Pandt</span>
          </h1>
          <p className="text-xl text-gray-400 max-w-2xl">
            HBO IT student focused on web development and UI/UX, preparing for a third-year internship in software development and game development.
          </p>
          
          
          <div className="flex gap-6 pt-8">
            <a 
              href="https://github.com/HPandt" 
              target="_blank" 
              rel="noopener noreferrer"
              className="p-3 border-2 border-gray-700 hover:border-yellow-400 transition-colors rounded-lg group"
            >
              <Github className="w-6 h-6 group-hover:text-yellow-400 transition-colors" />
            </a>
            <a 
              href="mailto:hunterpandt1@hotmail.com" 
              className="p-3 border-2 border-gray-700 hover:border-yellow-400 transition-colors rounded-lg group"
            >
              <Mail className="w-6 h-6 group-hover:text-yellow-400 transition-colors" />
            </a>
            <a 
              href="https://linkedin.com/in/hunter-pandt/" 
              target="_blank" 
              rel="noopener noreferrer"
              className="p-3 border-2 border-gray-700 hover:border-yellow-400 transition-colors rounded-lg group"
            >
              <Linkedin className="w-6 h-6 group-hover:text-yellow-400 transition-colors" />
            </a>
          </div>
        </div>
      </div>
      <article class="">
        <img src="/src/assets/Images/Profile-foto.png" alt="Hero Image" class="w-96 h-auto rounded-lg mt-12" />
        <header>
            
            
        </header>
    </article>

      <button 
        onClick={scrollToProjects}
        className="absolute bottom-12 left-1/2 -translate-x-1/2 animate-bounce"
      >
        <ArrowDown className="w-8 h-8 text-yellow-400" />
      </button>
    </section>
</template>