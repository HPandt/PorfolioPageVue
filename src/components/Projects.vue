<script setup>
import { ExternalLink, Star, GitFork, Calendar } from 'lucide-vue-next'
import { ref, onMounted } from 'vue'

const repositories = ref([])

const fetchRepositories = async () => {
  try {
    const response = await fetch('https://api.github.com/users/HPandt/repos')
    repositories.value = await response.json()
    console.log(repositories.value)
  } catch (error) {
    console.error('Error fetching repositories:', error)
  }
}

onMounted(() => {
  fetchRepositories()
})

const getLanguageColor = (language) => {
  const colors = {
    'JavaScript': 'bg-yellow-400',
    'TypeScript': 'bg-blue-400',
    'Python': 'bg-blue-600',
    'Java': 'bg-red-500',
    'C#': 'bg-purple-500',
    'PHP': 'bg-indigo-500',
    'HTML': 'bg-orange-500',
    'CSS': 'bg-blue-500',
    'Go': 'bg-cyan-400',
    'Rust': 'bg-orange-600',
  }
  return colors[language] || 'bg-gray-500'
}

const formatDate = (dateString) => {
  const date = new Date(dateString)
  return date.toLocaleDateString('en-US', { month: 'short', year: 'numeric' })
}
</script>

<template>
  <section id="projects" class="min-h-screen bg-zinc-950 text-white px-6 py-24">
    <div class="max-w-7xl mx-auto">
      <div class="mb-16">
        <h2 class="text-5xl md:text-6xl font-bold mb-4">
          FEATURED <span class="text-yellow-400">PROJECTS</span>
        </h2>
        <p class="text-xl text-gray-400">
          A collection of my work from GitHub
        </p>
      </div>

      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
        <a
          v-for="repo in repositories"
          :key="repo.id"
          :href="repo.html_url"
          target="_blank"
          rel="noopener noreferrer"
          class="group bg-zinc-900 border-2 border-zinc-800 hover:border-yellow-400 rounded-xl p-6 transition-all duration-300 hover:scale-105"
        >
          <div class="flex items-start justify-between mb-4">
            <h3 class="text-2xl font-bold group-hover:text-yellow-400 transition-colors">
              {{ repo.name }}
            </h3>
            <ExternalLink class="w-5 h-5 text-gray-500 group-hover:text-yellow-400 transition-colors" />
          </div>

          <p v-if="repo.description" class="text-gray-400 mb-4 line-clamp-2">
            {{ repo.description }}
          </p>

          <div class="flex items-center gap-4 mb-4 text-sm text-gray-500">
            <div v-if="repo.language" class="flex items-center gap-2">
              <span :class="`w-3 h-3 rounded-full ${getLanguageColor(repo.language)}`"></span>
              <span>{{ repo.language }}</span>
            </div>
            <div class="flex items-center gap-1">
              <Star class="w-4 h-4" />
              <span>{{ repo.stargazers_count }}</span>
            </div>
            <div class="flex items-center gap-1">
              <GitFork class="w-4 h-4" />
              <span>{{ repo.forks_count }}</span>
            </div>
          </div>

          <div class="flex items-center gap-2 text-xs text-gray-600">
            <Calendar class="w-3 h-3" />
            <span>Updated {{ formatDate(repo.updated_at) }}</span>
          </div>
        </a>
      </div>

      <div v-if="repositories.length === 0" class="text-center py-20">
        <p class="text-gray-500 text-xl">No public repositories found</p>
      </div>
    </div>
  </section>
</template>