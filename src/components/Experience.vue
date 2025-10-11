<template>
  <section id="experience" class="py-20 bg-white">
    <div class="max-w-5xl mx-auto px-6 text-center">
      <h2 class="text-3xl font-bold text-blue-600 mb-10">Experience</h2>

      <div class="space-y-8 text-left">
        <div v-for="(exp, index) in experiences" :key="index" class="bg-gray-50 p-6 rounded-2xl shadow-md hover:shadow-lg transition">
          <h3 class="text-xl font-semibold mb-1">{{ exp.role }}</h3>
          <p class="text-gray-600 mb-2">{{ exp.company }}</p>
          <p class="text-gray-500 text-sm">{{ exp.duration }}</p>
          <p class="text-gray-700 mt-2">{{ exp.details }}</p>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const experiences = [
  {
    role: "Full Stack Web Developer Intern",
    company: "Big-Si-Bucks, Chennai",
    duration: "June 9, 2025 – June 28, 2025",
    details: "Worked on developing full-stack web applications using HTML, CSS, JavaScript, and Java Servlets with Firebase integration."
  },
  {
    role: "Cloud Intern",
    company: "Pinnacle Labs",
    duration: "June 9, 2025 – July 8, 2025",
    details: "Gained hands-on experience in cloud technologies, deployed applications on cloud platforms, and optimized cloud resources for better performance."
  },
  {
    role: "Full Stack Intern",
    company: "Unified Mentorship",
    duration: "July 1, 2025 – Present",
    details: "Building a mentorship platform with full-stack development including Java backend, servlets, and cloud-integrated frontend with real-time chat and resources dashboard."
  }
]
</script>
