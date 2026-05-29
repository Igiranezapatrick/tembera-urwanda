<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
import { RouterLink, RouterView } from 'vue-router'

// Track which dropdown is currently active (null if none)
const activeDropdown = ref(null)

// Toggle specific dropdown and close others
const toggleDropdown = (dropdownName) => {
  if (activeDropdown.value === dropdownName) {
    activeDropdown.value = null
  } else {
    activeDropdown.value = dropdownName
  }
}

// Close dropdown when clicking outside
const onClickOutside = (event) => {
  if (!event.target.closest('.nav-dropdown')) {
    activeDropdown.value = null
  }
}

onMounted(() => {
  document.addEventListener('click', onClickOutside)
})

onUnmounted(() => {
  document.removeEventListener('click', onClickOutside)
})
</script>

<template>
  <nav class="sticky top-0 z-50 bg-gradient-to-r from-green-700 to-green-800 text-white px-8 py-4 flex items-center justify-between shadow-lg">
    <!-- Logo Section -->
    <div class="flex items-center gap-3 flex-shrink-0">
      <img src="../assets/sos.svg" class="h-10 w-10 drop-shadow-lg" alt="Logo">
      <span class="text-xl font-bold hidden sm:inline">Tembera Urwanda</span>
    </div>

    <!-- Navigation Links -->
    <ul class="flex gap-6 md:gap-10 items-center justify-end flex-wrap list-none p-0 m-0">
      <li class="hover:text-yellow-200 transition duration-300">
        <RouterLink to="/" class="font-semibold flex items-center">Home</RouterLink>
      </li>
      <li class="hover:text-yellow-200 transition duration-300">
        <RouterLink to="/about" class="font-semibold flex items-center">About</RouterLink>
      </li>
      <li class="hover:text-yellow-200 transition duration-300">
        <RouterLink to="/services" class="font-semibold flex items-center">Services</RouterLink>
      </li>

      <!-- Gallery Dropdown -->
      <li class="nav-dropdown relative cursor-pointer py-2">
        <span 
          @click="toggleDropdown('gallery')"
          class="hover:text-yellow-200 flex items-center gap-2 select-none font-semibold transition duration-300"
        >
          Gallery 
          <span class="text-xs transition-transform duration-300" :class="{ 'rotate-180': activeDropdown === 'gallery' }">
            ▼
          </span>
        </span>
        <!-- Dropdown Menu Box -->
        <ul v-if="activeDropdown === 'gallery'" class="absolute left-0 top-full mt-0 bg-white text-gray-900 rounded-lg shadow-xl py-3 w-48 z-50 border-t-4 border-green-600">
          <li class="hover:bg-green-50">
            <RouterLink to="/gallery/photos" class="block px-4 py-3 hover:text-yellow-700 font-semibold transition-colors">📸 Photos</RouterLink>
          </li>
          <li class="hover:bg-green-50 border-t border-gray-200">
            <RouterLink to="/gallery/videos" class="block px-4 py-3 hover:text-yellow-700 font-semibold transition-colors">🎥 Videos</RouterLink>
          </li>
        </ul>
      </li>

      <!-- Destination Dropdown -->
      <li class="nav-dropdown relative cursor-pointer py-2">
        <span 
          @click="toggleDropdown('destinations')"
          class="hover:text-yellow-200 flex items-center gap-2 select-none font-semibold transition duration-300"
        >
          Destinations 
          <span class="text-xs transition-transform duration-300" :class="{ 'rotate-180': activeDropdown === 'destinations' }">
            ▼
          </span>
        </span>
        <!-- Dropdown Menu Box -->
        <ul v-if="activeDropdown === 'destinations'" class="absolute left-0 top-full mt-0 bg-white text-gray-900 rounded-lg shadow-xl py-3 w-48 z-50 border-t-4 border-green-600">
          <li class="hover:bg-green-50">
            <RouterLink to="/dest/northern" class="block px-4 py-3 hover:text-yellow-700 font-semibold transition-colors">⛰️ Northern</RouterLink>
          </li>
          <li class="hover:bg-green-50 border-t border-gray-200">
            <RouterLink to="/dest/southern" class="block px-4 py-3 hover:text-yellow-700 font-semibold transition-colors">🌄 Southern</RouterLink>
          </li>
          <li class="hover:bg-green-50 border-t border-gray-200">
            <RouterLink to="/dest/eastern" class="block px-4 py-3 hover:text-yellow-700 font-semibold transition-colors">🌅 Eastern</RouterLink>
          </li>
          <li class="hover:bg-green-50 border-t border-gray-200">
            <RouterLink to="/dest/western" class="block px-4 py-3 hover:text-yellow-700 font-semibold transition-colors">🌆 Western</RouterLink>
          </li>
          <li class="hover:bg-green-50 border-t border-gray-200">
            <RouterLink to="/dest/kigali" class="block px-4 py-3 hover:text-yellow-700 font-semibold transition-colors">🏙️ Kigali</RouterLink>
          </li>
        </ul>
      </li>

      <li class="hover:text-yellow-200 transition duration-300">
        <RouterLink to="/contacts" class="font-semibold flex items-center">Contact</RouterLink>
      </li>
    </ul>
  </nav>

  <!-- Main Content Area -->
  <main class="min-h-screen bg-gradient-to-b from-gray-50 to-white">
    <RouterView />
  </main>
</template>
