<template>
  <section id="projects" class="py-20 bg-gray-50">
    <div class="max-w-6xl mx-auto px-6 text-center">
      <h2 class="text-3xl font-bold text-blue-600 mb-10">Projects</h2>

      <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
        <div 
          v-for="(project, index) in projects" 
          :key="index" 
          class="bg-white p-6 rounded-2xl shadow-lg hover:scale-105 transition"
          >
          <img :src="project.image" :alt="project.title" class="mb-4 rounded-lg shadow-md">
          <h3 class="text-xl font-semibold mb-2">{{ project.title }}</h3>
          <p class="text-gray-600 mb-2">{{ project.description }}</p>
          <a v-if="project.link" :href="project.link" target="_blank" class="text-blue-600 font-medium hover:underline">View Project</a>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const projects = [
  {
    title: "Geo-Tagged Fish Logger",
    description: "A Progressive Web App that allows fishermen to log fish catches with GPS locations, images, and species information. Integrated with Firebase and AI-powered species identification.",
    image: new URL('../assets/geo_fish_logger.png', import.meta.url).href,
    link: "https://geo-tagged-fish-catcher.web.app"
  },
]
</script>
