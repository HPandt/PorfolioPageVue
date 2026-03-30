<script setup>
import { Briefcase } from 'lucide-vue-next'

const experiences = [
  {
    role: 'Factory Worker',
    company: 'Image Building',
    period: 'September 2020 - March 2021',
    location: 'Katwijk aan het zee, Netherlands',
    description: 'Created and assembled buildboards for advertisement displays, and maintained a clean and organized workspace. Developed attention to detail and teamwork skills in a fast-paced environment.',
  },
  {
    role: 'Internship - Application Developer',
    company: 'RoadGuide / Forlago',
    period: 'September 2023 - March 2024',
    location: 'Den Haag, Netherlands',
    description: 'Worked with another intern on creating a web application to help drivers find the cheapest fuel station & parking spots. Developed using FLutter for the front and back-end, with Apis for data retrieval. Gained experience in full-stack development, problem-solving, and working in a team environment.',
  },
  {
    role: 'Shelf Stocker on lease',
    company: 'Young Capital',
    period: '2025 - Present',
    location: 'Den Haag, Netherlands',
    description: 'Responsible for stocking shelves, organizing inventory, and ensuring a clean and safe shopping environment. Developed strong organizational skills, attention to detail, and the ability to work efficiently in a team setting.',
  },
]
</script>

<template>
  <section id="experience" class="min-h-screen bg-zinc-950 text-white px-6 py-24">
    <div class="max-w-4xl mx-auto">
      <h2 class="text-5xl md:text-6xl font-bold mb-12">
        WORK <span class="text-yellow-400">EXPERIENCE</span>
      </h2>

      <div class="space-y-8">
        <div 
          v-for="(exp, index) in experiences"
          :key="index"
          class="bg-zinc-900 border-2 border-zinc-800 rounded-xl p-8 hover:border-yellow-400 transition-colors"
        >
          <div class="flex items-start gap-4">
            <div class="p-3 bg-yellow-400/10 rounded-lg">
              <Briefcase class="w-6 h-6 text-yellow-400" />
            </div>
            <div class="flex-1">
              <h3 class="text-2xl font-bold mb-2">{{ exp.role }}</h3>
              <p class="text-yellow-400 text-lg mb-2">{{ exp.company }}</p>
              <p class="text-gray-500 text-sm mb-1">{{ exp.period }}</p>
              <p class="text-gray-600 text-sm mb-4">{{ exp.location }}</p>
              <p class="text-gray-400 leading-relaxed">{{ exp.description }}</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>