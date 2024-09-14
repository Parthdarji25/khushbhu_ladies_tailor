<template>
  <div>
    <!-- New Banner Section -->
    <section class="relative mt-8">
      <div class="container mx-auto">
        <div class="relative overflow-hidden h-80 md:h-96 rounded-lg shadow-lg">
          <!-- Banner Image -->
          <img
            src="public/Images/kurtis_1.jpg"
            alt="Tailoring Services Banner"
            class="w-full h-full object-cover"
          />
          <!-- Optional Text Overlay -->
          <div
            class="absolute inset-0 bg-black bg-opacity-50 flex items-center justify-center text-white text-center p-6"
          >
            <div>
              <h2 class="text-2xl md:text-4xl font-bold mb-4">
                Quality Tailoring Services
              </h2>
              <p class="text-lg mb-6">
                Custom fitting and alterations for all your needs
              </p>
              <NuxtLink
                to="/contact"
                class="bg-indigo-600 hover:bg-indigo-700 text-white px-6 py-3 rounded-full text-lg"
              >
                Contact Us Now
              </NuxtLink>
            </div>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>
