<template>
  <section id="certifications" class="py-20 bg-gray-50">
    <div class="max-w-6xl mx-auto px-6 text-center">
      <h2 class="text-3xl font-bold text-blue-600 mb-10">Certifications</h2>

      <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
        <div 
          v-for="(cert, index) in certifications" 
          :key="index" 
          class="bg-white p-6 rounded-2xl shadow-lg hover:scale-105 transition cursor-pointer"
          @click="openModal(cert)"
        >
          <img :src="cert.image" :alt="cert.title" class="mb-4 rounded-lg shadow-md">
          <h3 class="text-xl font-semibold mb-2">{{ cert.title }}</h3>
          <p class="text-gray-600 mb-2">{{ cert.institute }}</p>
          <a v-if="cert.link" :href="cert.link" target="_blank" class="text-blue-600 font-medium hover:underline">View Certificate</a>
        </div>
      </div>

      <!-- Modal -->
      <div v-if="showModal" class="fixed inset-0 bg-black bg-opacity-70 flex justify-center items-center z-50">
        <div class="bg-white rounded-lg max-w-3xl w-full p-4 relative">
          <button @click="closeModal" class="absolute top-2 right-2 text-gray-600 text-2xl font-bold">&times;</button>
          <img :src="currentCert.image" :alt="currentCert.title" class="rounded-lg mx-auto">
          <h3 class="text-xl font-semibold mt-4">{{ currentCert.title }}</h3>
          <p class="text-gray-600">{{ currentCert.institute }}</p>
          <a v-if="currentCert.link" :href="currentCert.link" target="_blank" class="text-blue-600 font-medium hover:underline">View Certificate</a>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'

// Helper function to get correct image path in Vite
const getImageUrl = (filename) => new URL(`../assets/${filename}`, import.meta.url).href

const certifications = [
  { title: "Demystifying Networks", institute: "NPTEL | Score: 63 | Elite", image: getImageUrl('cert_nptel_networks.jpg') },
  { title: "Python for Data Science", institute: "NPTEL | Score: 68 | Elite", image: getImageUrl('cert_nptel_python.jpg') },
  { title: "Fundamentals of Java Programming", institute: "Board Infinity", image: getImageUrl('cert_java_boardinfinity.jpg') },
  { title: "Java Essentials", institute: "Cisco", image: getImageUrl('cert_java_cisco.jpg'), link: "https://www.credly.com/badges/56581a0c-5119-43a6-a7c3-a78fc8e4ad0e/linked_in_profile" },
  { title: "AWS Academy Cloud Foundations", institute: "AWS Academy", image: getImageUrl('cert_aws_foundations.jpg'), link: "https://www.credly.com/badges/7d587627-8b07-4d12-bf63-3c5f81f1364d/linked_in_profile" },
  { title: "AWS Generative AI Foundations", institute: "AWS Academy", image: getImageUrl('cert_aws_ai.jpg'), link: "https://www.credly.com/badges/dda141b1-7279-42ef-b2d1-2b35689d82b9/linked_in_profile" },
  { title: "Networking Basics", institute: "Cisco", image: getImageUrl('cert_networking_cisco.jpg'), link: "https://www.credly.com/badges/f764f1ff-9977-4aaf-8ac1-f0153ce3139c/linked_in_profile" },
  { title: "Linux Unhatched", institute: "Cisco", image: getImageUrl('cert_linux_unhatched.jpg'), link: "https://www.credly.com/badges/447a8524-cb44-40c8-840a-98869f2b7e4c/linked_in_profile" }
]

const showModal = ref(false)
const currentCert = ref({})

function openModal(cert) {
  currentCert.value = cert
  showModal.value = true
}

function closeModal() {
  showModal.value = false
}
</script>
