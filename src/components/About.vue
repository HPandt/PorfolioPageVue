<script setup>
const skills = ['C#', 'PHP', 'Java', 'HTML/CSS', 'JavaScript', 'SQL', 'NoSQL', 'Git']
</script>

<template>
  <section id="about" class="min-h-screen bg-black text-white px-6 py-24">
    <div class="max-w-4xl mx-auto">
      <h2 class="text-5xl md:text-6xl font-bold mb-12">
        ABOUT <span class="text-yellow-400">ME</span>
      </h2>

      <div class="space-y-8">
        <div class="bg-zinc-900 border-2 border-zinc-800 rounded-xl p-8 flex flex-col gap-4">
          <h3 class="text-2xl font-bold mb-4 text-yellow-400">Bio</h3>
          <p class="text-gray-400 text-lg leading-relaxed">
            I’m a second-year HBO IT student at Inholland Haarlem with a focus on web development and UI/UX design. During my studies, I’ve worked on building web applications using technologies such as HTML/CSS, JavaScript, PHP, and C#, with attention to usability, structure, and maintainability.
          </p>
          <p class="text-gray-400 text-lg leading-relaxed">
            I enjoy working on back-end functionality and currently having an interest in front-end, including handling data with SQL and NoSQL databases and using Git for version control in team projects. I’m continuously developing my problem-solving skills and learning how to write clean, reliable code.
          </p>
          <p class="text-gray-400 text-lg leading-relaxed">
            I’m currently preparing for my third-year internship, where I’m looking to gain hands-on experience, contribute to real projects, and grow as a developer in a professional environment.
          </p>
        </div>

        <div class="bg-zinc-900 border-2 border-zinc-800 rounded-xl p-8">
          <h3 class="text-2xl font-bold mb-6 text-yellow-400">Skills</h3>
          <div class="grid grid-cols-2 md:grid-cols-3 gap-4">
            <div 
              v-for="skill in skills"
              :key="skill"
              class="bg-black border border-zinc-700 rounded-lg px-4 py-3 text-center hover:border-yellow-400 transition-colors"
            >
              {{ skill }}
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>