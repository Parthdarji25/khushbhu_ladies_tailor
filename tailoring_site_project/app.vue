<template>
  <div class="min-h-screen flex flex-col bg-gray-100">
    <!-- Header -->
    <header class="bg-indigo-700 text-white shadow-md py-4">
      <nav class="container mx-auto flex justify-between items-center px-6">
        <h1
          class="text-3xl md:text-4xl font-bold tracking-wider gradient-text animate-title"
        >
          Khushbu Ladies Tailoring
        </h1>
        <button
          class="block md:hidden text-white focus:outline-none"
          @click="isMenuOpen = !isMenuOpen"
        >
          <svg
            class="h-6 w-6"
            fill="none"
            stroke="currentColor"
            viewBox="0 0 24 24"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M4 6h16M4 12h16m-7 6h7"
            />
          </svg>
        </button>
        <ul
          :class="{ block: isMenuOpen, hidden: !isMenuOpen }"
          class="md:flex md:flex-row space-y-4 md:space-y-0 md:space-x-6 absolute md:static bg-indigo-700 md:bg-transparent top-16 right-0 w-full md:w-auto z-20"
        >
          <li class="text-center">
            <NuxtLink to="/" class="nav-link" @click="closeMenu">Home</NuxtLink>
          </li>
          <li class="text-center">
            <NuxtLink to="/services" class="nav-link" @click="closeMenu"
              >Services</NuxtLink
            >
          </li>
          <li class="text-center">
            <NuxtLink to="/about" class="nav-link" @click="closeMenu"
              >About</NuxtLink
            >
          </li>
          <li class="text-center">
            <NuxtLink to="/contact" class="nav-link" @click="closeMenu"
              >Contact</NuxtLink
            >
          </li>
        </ul>
      </nav>
    </header>

    <!-- Main Content -->
    <main class="flex-grow">
      <NuxtPage />
    </main>

    <!-- Footer -->
    <footer class="bg-gray-800 text-white py-6 mt-4">
      <div
        class="container mx-auto flex flex-col md:flex-row justify-between items-center text-center md:text-left space-y-6 md:space-y-0"
      >
        <!-- Footer links section -->
        <ul
          class="flex flex-col md:flex-row justify-center md:justify-start space-y-2 md:space-y-0 md:space-x-6"
        >
          <li>
            <NuxtLink to="/" class="footer-link">Home</NuxtLink>
          </li>
          <li>
            <NuxtLink to="/services" class="footer-link">Services</NuxtLink>
          </li>
          <li>
            <NuxtLink to="/about" class="footer-link">About</NuxtLink>
          </li>
          <li>
            <NuxtLink to="/contact" class="footer-link">Contact</NuxtLink>
          </li>
        </ul>

        <!-- Address and Office Hours section -->
        <div class="mt-4 md:mt-0 text-center md:text-left">
          <p class="text-sm font-semibold">Address:</p>
          <p class="text-sm">
            Shop No-15, B/20, Sector 7, <br />Shanti Nagar, Mira Road East,
            <br />Mira Bhayandar, Maharashtra 401107
          </p>

          <p class="text-sm font-semibold mt-4">Shop Hours:</p>
          <p class="text-sm">Mon: Closed</p>
          <p class="text-sm">Tue - Sun: 9 AM - 9 PM</p>
        </div>

        <!-- Contact section -->
        <div class="mt-4 md:mt-0 text-center md:text-left">
          <p class="text-sm font-semibold">Contact us:</p>
          <p class="text-sm font-semibold mt-4">
            Rajesh Bhai Darji : +91 9870640577
          </p>

          <p class="text-sm">
            <a href="mailto:info@khushbutailoring.com" class="text-indigo-400"
              >info@khushbutailoring.com</a
            >
          </p>
        </div>

        <!-- Copyright section -->
        <div class="mt-4 md:mt-0 text-center">
          <p class="text-sm">
            &copy; 2024 Khushbu Ladies Tailoring. All Rights Reserved.
          </p>
        </div>
      </div>
    </footer>
  </div>
</template>

<script setup>
import { ref } from "vue";

// State to track whether the mobile menu is open
const isMenuOpen = ref(false);

// Method to close the menu when a link is clicked
const closeMenu = () => {
  isMenuOpen.value = false;
};
</script>

<style scoped>
/* Gradient text animation */
.gradient-text {
  background: linear-gradient(90deg, #f3a9b4, #b4a7f3, #a8f3b4);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

/* Animated text effect */
@keyframes titleAnimation {
  0% {
    transform: translateY(0);
  }
  50% {
    transform: translateY(-10px);
    color: #ffcccb;
  }
  100% {
    transform: translateY(0);
  }
}

.animate-title {
  animation: titleAnimation 2s infinite;
}

/* Custom CSS for the navigation links */
.nav-link {
  text-decoration: none;
  color: white;
  font-size: 1rem;
  font-weight: 500;
  transition: color 0.3s ease, border-bottom 0.3s ease;
  position: relative;
}

.nav-link:hover {
  color: #f3f4f6;
}

.nav-link::after {
  content: "";
  position: absolute;
  bottom: -4px;
  left: 0;
  width: 0;
  height: 2px;
  background-color: #f3f4f6;
  transition: width 0.3s ease;
}

.nav-link:hover::after {
  width: 100%;
}

/* Responsive design */
@media (max-width: 768px) {
  .nav-link {
    font-size: 0.875rem;
  }

  header {
    padding: 1rem;
  }

  /* Center the footer content on mobile */
  footer {
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: center;
  }

  /* Menu changes for mobile */
  ul {
    text-align: left;
  }
}

/* Flexbox and responsive design for footer */
.footer-link {
  text-decoration: none;
  color: white;
  font-size: 0.875rem;
  font-weight: 500;
  transition: color 0.3s ease, border-bottom 0.3s ease;
  position: relative;
}

.footer-link:hover {
  color: #f3f4f6;
}

.footer-link::after {
  content: "";
  position: absolute;
  bottom: -4px;
  left: 0;
  width: 0;
  height: 2px;
  background-color: #f3f4f6;
  transition: width 0.3s ease;
}

.footer-link:hover::after {
  width: 100%;
}

/* Responsive design for smaller screens */
@media (max-width: 768px) {
  footer {
    flex-direction: column;
    text-align: center;
  }

  .footer-link {
    font-size: 0.875rem;
  }
}
</style>
