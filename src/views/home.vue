<script setup>
// 1. Import the image asset
import gorillaBg from '../assets/gorilla2.jpg'
</script>
<template>
  <section class="min-h-screen bg-gradient-to-b from-green-50 to-white bg-cover bg-center bg-no-repeat" :style="{ backgroundImage: `url(${gorillaBg})` }">
    <!-- Hero Section -->
    <div 
      class="min-h-[70vh] flex flex-col items-center justify-center text-center px-4 py-20 bg-cover bg-center relative"
    >
      <!-- Background Overlay for text readability -->
      <div class="absolute inset-0 bg-green-950/40 mix-blend-multiply"></div>

      <!-- Hero Content -->
      <div class="max-w-4xl mx-auto relative z-10">
        <!-- <div class="mb-6 inline-block px-4 py-2 bg-green-100 text-green-700 rounded-full text-sm font-semibold tracking-wider">
          🌍 DISCOVER AFRICA'S GEM
        </div> -->
        
        <h1 class="text-6xl md:text-7xl font-extrabold text-white tracking-tight mb-6 leading-tight drop-shadow-md">
          WELCOME TO<br />
          <span class="text-transparent bg-clip-text bg-gradient-to-r from-green-400 to-emerald-300">TEMBERA URWANDA</span>
        </h1>
        
        <p class="text-xl md:text-2xl text-gray-100 mb-8 leading-relaxed max-w-2xl mx-auto drop-shadow-sm">
          Explore the Land of a Thousand Hills - Rwanda's breathtaking natural beauty, rich culture, and unforgettable experiences await you.
        </p>
        
        <div class="flex flex-col sm:flex-row gap-4 justify-center">
          <button class="px-8 py-3 bg-green-600 text-white rounded-lg font-semibold hover:bg-green-700 transition shadow-lg hover:shadow-xl">
            Start Exploring
          </button>
          <button class="px-8 py-3 border-2 border-white text-white rounded-lg font-semibold hover:bg-white/10 transition backdrop-blur-sm">
            Learn More
          </button>
        </div>
      </div>
    </div>
  </section>

    <!-- Why Choose Rwanda
    <section class="py-20 px-4 bg-gradient-to-r from-green-50 to-emerald-50">
      <div class="max-w-6xl mx-auto">
        <h2 class="text-4xl font-bold text-center text-gray-800 mb-12">Why Choose Rwanda?</h2>
        
        <div class="grid grid-cols-1 md:grid-cols-4 gap-6">
          <div class="text-center">
            <div class="text-5xl mb-4">✈️</div>
            <h3 class="text-xl font-bold text-gray-800 mb-2">Easy Access</h3>
            <p class="text-gray-600">Modern airport and good connectivity to major cities worldwide</p>
          </div>
          <div class="text-center">
            <div class="text-5xl mb-4">🛡️</div>
            <h3 class="text-xl font-bold text-gray-800 mb-2">Safe & Secure</h3>
            <p class="text-gray-600">One of Africa's safest destinations with excellent hospitality</p>
          </div>
          <div class="text-center">
            <div class="text-5xl mb-4">🏨</div>
            <h3 class="text-xl font-bold text-gray-800 mb-2">Luxury Stays</h3>
            <p class="text-gray-600">World-class hotels and resorts for every budget</p>
          </div>
          <div class="text-center">
            <div class="text-5xl mb-4">🌿</div>
            <h3 class="text-xl font-bold text-gray-800 mb-2">Nature & Culture</h3>
            <p class="text-gray-600">Rich biodiversity and vibrant cultural experiences</p>
          </div>
        </div>
      </div>
    </section> -->
</template>