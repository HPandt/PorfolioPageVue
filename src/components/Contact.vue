<script setup>
import { Github, Linkedin, Mail, ExternalLink } from 'lucide-vue-next'

const socialLinks = [
  {
    name: 'GitHub',
    icon: Github,
    href: 'https://github.com/HPandt',
    description: 'Check out my repositories and contributions',
  },
  {
    name: 'LinkedIn',
    icon: Linkedin,
    href: 'https://www.linkedin.com/in/hunter-pandt/',
    description: 'Connect with me professionally',
  },
  {
    name: 'Email',
    icon: Mail,
    href: 'mailto:hunterpandt1@hotmail.com',
    description: 'Send me an email',
  },
]

const opportunities = [
  'Front-End Development',
  'Back-End APIs',
  'Testing & QA',
  'Game Development',
  'Team Projects (Agile)',
]

const currentYear = new Date().getFullYear()
</script>

<template>
  <section id="contact" class="min-h-screen bg-black text-white px-6 py-24">
    <div class="max-w-4xl mx-auto">
      <h2 class="text-3xl md:text-6xl font-bold mb-12">
        LET'S <span class="text-yellow-400">CONNECT</span>
      </h2>

      <div class="space-y-12">
        

        <div class="grid md:grid-cols-3 gap-6">
          <a
            v-for="link in socialLinks"
            :key="link.name"
            :href="link.href"
            :target="link.name !== 'Email' ? '_blank' : undefined"
            :rel="link.name !== 'Email' ? 'noopener noreferrer' : undefined"
            class="group bg-zinc-900 border-2 border-zinc-800 hover:border-yellow-400 rounded-xl p-8 transition-all duration-300 hover:scale-105"
          >
            <div class="flex items-center justify-between mb-4">
              <div class="p-4 bg-yellow-400/10 rounded-lg group-hover:bg-yellow-400/20 transition-colors">
                <component :is="link.icon" class="w-8 h-8 text-yellow-400" />
              </div>
              <ExternalLink class="w-5 h-5 text-gray-600 group-hover:text-yellow-400 transition-colors" />
            </div>
            <h3 class="text-2xl font-bold mb-2 group-hover:text-yellow-400 transition-colors">
              {{ link.name }}
            </h3>
            <p class="text-gray-500">
              {{ link.description }}
            </p>
          </a>
        </div>

        <div class="bg-zinc-900 border-2 border-zinc-800 rounded-xl p-8 md:p-12 text-center">
          <h3 class="text-3xl font-bold mb-4">Open to Opportunities</h3>
          <p class="text-xl text-gray-400 mb-6">
            Currently seeking a third-year HBO IT internship in Web Development or Game Development, where I can apply my skills, learn from a team, and gain hands-on experience in a real-world environment.
          </p>
          <div class="flex flex-wrap justify-center gap-4">
            <span v-for="opp in opportunities" :key="opp" class="px-4 py-2 bg-black border border-zinc-700 rounded-lg text-sm">
              {{ opp }}
            </span>
          </div>
        </div>
      </div>
    </div>

    <footer class="mt-24 pt-12 border-t border-zinc-800 text-center text-gray-500">
      <p>&copy; {{ currentYear }} Hunter. All rights reserved.</p>
    </footer>
  </section>
</template>