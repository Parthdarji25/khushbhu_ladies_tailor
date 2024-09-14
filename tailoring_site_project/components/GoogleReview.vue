<template>
  <!-- Google Reviews Section -->
  <section class="bg-white py-8">
    <div class="container mx-auto px-6">
      <div class="flex items-center mb-6">
        <svg
          class="w-8 h-8 text-red-600 mr-2"
          fill="currentColor"
          viewBox="0 0 24 24"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            d="M12 17.27L18.18 21 16.54 13.97 22 9.24l-7.19-.62L12 2 9.19 8.62 2 9.24l5.46 4.73L5.82 21z"
          />
        </svg>
        <h2>
          <img src="../public/social.png" alt="" class="google-image" />
        </h2>
        <h2 class="text-3xl font-bold flex items-center ml-3 mt-2">Reviews</h2>
      </div>
      <!-- Custom Carousel -->
      <div class="relative">
        <div class="carousel overflow-hidden">
          <div class="carousel-inner flex transition-transform duration-300">
            <div class="carousel-item flex-shrink-0 w-full">
              <div class="bg-gray-100 p-6 rounded-lg shadow-lg">
                <div class="flex items-center mb-4">
                  <svg
                    class="w-8 h-8 text-yellow-400 mr-2"
                    fill="currentColor"
                    viewBox="0 0 24 24"
                    xmlns="http://www.w3.org/2000/svg"
                  >
                    <path
                      d="M12 17.27L18.18 21 16.54 13.97 22 9.24l-7.19-.62L12 2 9.19 8.62 2 9.24l5.46 4.73L5.82 21z"
                    />
                  </svg>
                  <span class="text-lg font-semibold">4.5/5</span>
                </div>
                <p class="text-gray-700 mb-4">
                  "Amazing service! The tailoring was perfect and the attention
                  to detail was impeccable. Highly recommend!"
                </p>
                <p class="font-semibold">Sita Patel</p>
              </div>
            </div>
            <div class="carousel-item flex-shrink-0 w-full">
              <div class="bg-gray-100 p-6 rounded-lg shadow-lg">
                <div class="flex items-center mb-4">
                  <svg
                    class="w-8 h-8 text-yellow-400 mr-2"
                    fill="currentColor"
                    viewBox="0 0 24 24"
                    xmlns="http://www.w3.org/2000/svg"
                  >
                    <path
                      d="M12 17.27L18.18 21 16.54 13.97 22 9.24l-7.19-.62L12 2 9.19 8.62 2 9.24l5.46 4.73L5.82 21z"
                    />
                  </svg>
                  <span class="text-lg font-semibold">4.7/5</span>
                </div>
                <p class="text-gray-700 mb-4">
                  "Fantastic experience! The alterations were done quickly and
                  accurately. Will definitely come back!"
                </p>
                <p class="font-semibold">Ravi Kumar</p>
              </div>
            </div>
            <div class="carousel-item flex-shrink-0 w-full">
              <div class="bg-gray-100 p-6 rounded-lg shadow-lg">
                <div class="flex items-center mb-4">
                  <svg
                    class="w-8 h-8 text-yellow-400 mr-2"
                    fill="currentColor"
                    viewBox="0 0 24 24"
                    xmlns="http://www.w3.org/2000/svg"
                  >
                    <path
                      d="M12 17.27L18.18 21 16.54 13.97 22 9.24l-7.19-.62L12 2 9.19 8.62 2 9.24l5.46 4.73L5.82 21z"
                    />
                  </svg>
                  <span class="text-lg font-semibold">4.8/5</span>
                </div>
                <p class="text-gray-700 mb-4">
                  "Exceptional service and quality! The team here knows their
                  craft. Highly satisfied with my garments."
                </p>
                <p class="font-semibold">Meena Sharma</p>
              </div>
            </div>
          </div>
        </div>
        <button
          @click="prevSlide"
          class="absolute left-1/2 transform -translate-x-1/2 bottom-[-40px] bg-gray-800 text-white px-4 py-2 rounded-full carousel-control carousel-control-prev"
        >
          ❮
        </button>
        <button
          @click="nextSlide"
          class="absolute left-1/2 transform -translate-x-1/2 bottom-[-40px] bg-gray-800 text-white px-4 py-2 rounded-full carousel-control carousel-control-next"
        >
          ❯
        </button>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, onMounted } from "vue";

// Carousel state
const currentIndex = ref(0);
const totalSlides = ref(3); // Total number of slides

const updateCarousel = () => {
  const carouselInner = document.querySelector(".carousel-inner");
  const slideWidth = document.querySelector(".carousel-item").offsetWidth;
  const offset = -currentIndex.value * slideWidth;
  carouselInner.style.transform = `translateX(${offset}px)`;
};

const prevSlide = () => {
  currentIndex.value =
    (currentIndex.value - 1 + totalSlides.value) % totalSlides.value;
  updateCarousel();
};

const nextSlide = () => {
  currentIndex.value = (currentIndex.value + 1) % totalSlides.value;
  updateCarousel();
};

onMounted(() => {
  updateCarousel();
});
</script>

<style>
/* Carousel styles */
.carousel {
  position: relative;
  overflow: hidden;
}

.carousel-inner {
  display: flex;
  transition: transform 0.3s ease;
}

.carousel-item {
  flex-shrink: 0;
  width: 100%;
}

button {
  cursor: pointer;
  border: none;
  background-color: transparent;
}

/* Adjust button positioning */
.carousel-control {
  bottom: 8px; /* Position buttons below the carousel */
  left: 50%;
  transform: translateX(-50%);
  margin: 0px 0px 5px 110px;
}

.carousel-control-prev {
  left: calc(50% - 50px); /* Adjust as needed */
}

.carousel-control-next {
  left: calc(50% + 10px); /* Adjust as needed */
}

.google-image {
  width: 100px;
  margin: 15px 0px 0px 15px;
}
</style>
