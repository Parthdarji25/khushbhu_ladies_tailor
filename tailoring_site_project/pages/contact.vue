<template>
  <section class="py-16 bg-white">
    <div class="container mx-auto max-w-4xl">
      <!-- Section Heading -->
      <h2 class="text-4xl font-bold text-center mb-12">Contact Us</h2>

      <!-- Contact Information -->
      <div class="bg-gray-100 p-8 rounded-lg shadow-lg mb-16">
        <h3 class="text-2xl font-semibold mb-4">Our Contact Details</h3>
        <p class="text-lg text-gray-700 mb-2">
          <strong>Name:</strong> Khushbu Ladies Tailor
        </p>
        <p class="text-lg text-gray-700 mb-2">
          <strong>Address:</strong> Shop No-15, B/20, Sector 7, Shanti Nagar,
          Mira Road East, Mira Bhayandar, Maharashtra 401107
        </p>
        <p class="text-lg text-gray-700 mb-2">
          <strong>Phone:</strong> +91 9870640577 - Rajesh Bhai Darji
        </p>
        <p class="text-lg text-gray-700 mb-2">
          <strong>Email:</strong> info@khushbutailoring.com
        </p>

        <!-- Business Hours -->
        <div class="mt-6">
          <h4 class="text-xl font-semibold mb-3">Business Hours:</h4>
          <ul class="text-lg text-gray-700 space-y-2">
            <li><strong>Saturday:</strong> 9:30 am – 9:30 pm</li>
            <li><strong>Sunday:</strong> 9:30 am – 9:30 pm</li>
            <li><strong>Monday:</strong> Closed</li>
            <li><strong>Tuesday:</strong> 9:30 am – 9:30 pm</li>
            <li><strong>Wednesday:</strong> 9:30 am – 9:30 pm</li>
            <li><strong>Thursday:</strong> 9:30 am – 9:30 pm</li>
            <li><strong>Friday:</strong> 9:30 am – 9:30 pm</li>
          </ul>
        </div>
      </div>

      <!-- Separator -->
      <hr class="my-12 border-t-2 border-gray-300" />

      <!-- Customer Contact Form -->
      <div class="bg-gray-100 p-8 rounded-lg shadow-lg">
        <h3 class="text-2xl font-semibold mb-6">Get in Touch with Us</h3>
        <form class="space-y-6">
          <!-- Name Field -->
          <div>
            <label for="name" class="block text-gray-700 font-semibold"
              >Your Name</label
            >
            <input
              type="text"
              id="name"
              class="w-full px-4 py-2 rounded-lg border border-gray-300"
              placeholder="Enter your name"
              required
            />
          </div>

          <!-- Email Field -->
          <div>
            <label for="email" class="block text-gray-700 font-semibold"
              >Your Email</label
            >
            <input
              type="email"
              id="email"
              class="w-full px-4 py-2 rounded-lg border border-gray-300"
              placeholder="Enter your email"
              required
            />
          </div>

          <!-- Phone Field -->
          <div>
            <label for="phone" class="block text-gray-700 font-semibold"
              >Your Phone Number</label
            >
            <input
              type="text"
              id="phone"
              class="w-full px-4 py-2 rounded-lg border border-gray-300"
              placeholder="Enter your phone number"
            />
          </div>

          <!-- Message Field -->
          <div>
            <label for="message" class="block text-gray-700 font-semibold"
              >Your Message</label
            >
            <textarea
              id="message"
              class="w-full px-4 py-2 rounded-lg border border-gray-300"
              rows="5"
              placeholder="Enter your message"
              required
            ></textarea>
          </div>

          <!-- Submit Button -->
          <div class="text-center">
            <button
              type="submit"
              class="px-6 py-3 bg-indigo-600 hover:bg-indigo-700 text-white rounded-lg font-semibold"
            >
              Send Message
            </button>
          </div>
        </form>
      </div>
    </div>
  </section>
</template>

<script setup></script>

<style scoped></style>
