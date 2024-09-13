<template>
  <div class="min-h-screen flex flex-col bg-gray-100">
    <!-- Header -->
    <header class="bg-indigo-700 text-white shadow-md py-4">
      <nav class="container mx-auto flex justify-between items-center px-6">
        <h1
          class="text-4xl font-bold tracking-wider gradient-text animate-title"
        >
          Khushbu Ladies Tailoring
        </h1>
        <ul class="flex space-x-6">
          <li>
            <NuxtLink to="/" class="nav-link">Home</NuxtLink>
          </li>
          <li>
            <NuxtLink to="/services" class="nav-link">Services</NuxtLink>
          </li>
          <li>
            <NuxtLink to="/about" class="nav-link">About</NuxtLink>
          </li>
          <li>
            <NuxtLink to="/contact" class="nav-link">Contact</NuxtLink>
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
      <div class="container mx-auto text-center">
        <p class="text-sm">
          &copy; 2024 Khushbu Ladies Tailoring. All Rights Reserved.
        </p>
      </div>
    </footer>
  </div>
</template>

<script setup>
// Nothing specific here for now
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
}
</style>
