<template>
  <!-- Carousel Section -->
  <!-- Carousel Section -->
  <section class="relative bg-gray-900 h-screen">
    <div class="relative h-full overflow-hidden">
      <!-- Carousel Items -->
      <div
        v-for="(image, index) in images"
        :key="index"
        :class="[
          'absolute inset-0 transition-opacity duration-1000 ease-in-out',
          {
            'opacity-100': currentIndex === index,
            'opacity-0': currentIndex !== index,
          },
        ]"
      >
        <img
          :src="`/images/${image.src}`"
          :alt="image.title"
          class="w-full h-full object-cover"
        />
        <div
          class="absolute inset-0 flex items-center justify-center bg-black bg-opacity-50"
        >
          <div class="text-center text-white">
            <h2 class="text-5xl font-bold mb-4">{{ image.title }}</h2>
            <p class="text-lg mb-6">{{ image.subtitle }}</p>
            <NuxtLink
              to="/contact"
              class="px-6 py-3 bg-indigo-500 hover:bg-indigo-600 text-white rounded-lg font-semibold"
              >Book an Appointment</NuxtLink
            >
          </div>
        </div>
      </div>

      <!-- Navigation Controls -->
      <div class="absolute inset-0 flex items-center justify-between px-4">
        <!-- Previous Button -->
        <button
          @click="prevSlide"
          class="text-white bg-black bg-opacity-50 hover:bg-opacity-75 p-2 rounded-full"
        >
          <svg
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 24 24"
            stroke="currentColor"
            class="h-6 w-6"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M15 19l-7-7 7-7"
            />
          </svg>
        </button>
        <!-- Next Button -->
        <button
          @click="nextSlide"
          class="text-white bg-black bg-opacity-50 hover:bg-opacity-75 p-2 rounded-full"
        >
          <svg
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 24 24"
            stroke="currentColor"
            class="h-6 w-6"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M9 5l7 7-7 7"
            />
          </svg>
        </button>
      </div>
    </div>
  </section>

  <!-- Services Section -->
  <section class="py-16 bg-gray-100">
    <div class="container mx-auto">
      <h3 class="text-4xl font-bold text-center mb-8">Our Services</h3>
      <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
        <div class="bg-white p-6 rounded-lg shadow-lg">
          <img
            src="public/Images/kurtis_1.jpg"
            alt="Custom Dress"
            class="w-full h-48 object-cover rounded-t-lg mb-4"
          />
          <h4 class="text-2xl font-semibold mb-2">Custom Dress Design</h4>
          <p class="text-gray-600">
            Get your dream dress designed for special occasions.
          </p>
        </div>
        <div class="bg-white p-6 rounded-lg shadow-lg">
          <img
            src="public/Images/kurtis_1.jpg"
            alt="Alteration"
            class="w-full h-48 object-cover rounded-t-lg mb-4"
          />
          <h4 class="text-2xl font-semibold mb-2">Alterations</h4>
          <p class="text-gray-600">
            We provide perfect fitting with expert alteration services.
          </p>
        </div>
        <div class="bg-white p-6 rounded-lg shadow-lg">
          <img
            src="public/Images/kurtis_1.jpg"
            alt="Embroidery"
            class="w-full h-48 object-cover rounded-t-lg mb-4"
          />
          <h4 class="text-2xl font-semibold mb-2">Embroidery</h4>
          <p class="text-gray-600">
            Beautiful hand-crafted embroidery to add elegance.
          </p>
        </div>
      </div>
    </div>
  </section>

  <!-- Call to Action Section -->
  <section class="py-16 bg-indigo-600 text-white text-center">
    <h3 class="text-4xl font-bold mb-6">Ready to Look Your Best?</h3>
    <NuxtLink
      to="/contact"
      class="px-6 py-3 bg-white text-indigo-600 font-semibold rounded-lg hover:bg-gray-200"
      >Contact Us</NuxtLink
    >
  </section>
</template>

<script setup>
import { ref, onMounted } from "vue";

// Define the images for the carousel
const images = ref([
  {
    src: "kurtis_1.jpg",
    title: "Custom Tailoring for Ladies",
    subtitle: "Perfect Fit, Every Time. Made with Love and Precision.",
  },
  {
    src: "kurtis_2.jpg",
    title: "Beautiful Embroidery",
    subtitle: "Exquisite Hand-Crafted Embroidery Designs.",
  },
  {
    src: "kurtis_3.jpg",
    title: "Perfect Alterations",
    subtitle: "Alterations to Ensure the Perfect Fit for You.",
  },
]);

// Current slide index
const currentIndex = ref(0);

// Set interval for auto-sliding
onMounted(() => {
  setInterval(() => {
    nextSlide();
  }, 5000); // Change slide every 5 seconds
});

// Function to go to the previous slide
const prevSlide = () => {
  currentIndex.value =
    currentIndex.value === 0 ? images.value.length - 1 : currentIndex.value - 1;
};

// Function to go to the next slide
const nextSlide = () => {
  currentIndex.value =
    currentIndex.value === images.value.length - 1 ? 0 : currentIndex.value + 1;
};
</script>

<style scoped>
/* You can add component-specific styles here */
</style>
