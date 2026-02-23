<script setup>
import { onMounted, onUnmounted } from 'vue';

onMounted(() => {
  console.log("CarouselBanner mounted");
});

onUnmounted(() => {
  console.log("CarouselBanner unmounted");
});
</script>

<template>
  <div class="carousel w-full rounded-box h-64 md:h-96">
    <div id="slide1" class="carousel-item relative w-full">
      <img src="https://images.unsplash.com/photo-1542291026-7eec264c27ff?auto=format&fit=crop&q=80&w=1000" class="w-full object-cover" />
      <div class="absolute left-5 right-5 top-1/2 flex -translate-y-1/2 transform justify-between">
        <a href="#slide3" class="btn btn-circle">❮</a>
        <a href="#slide2" class="btn btn-circle">❯</a>
      </div>
      <div class="absolute bottom-5 left-1/2 -translate-x-1/2 text-white bg-black/50 p-4 rounded-lg text-center">
        <h2 class="text-3xl font-bold">New Summer Collection</h2>
        <p>Step into comfort with our latest releases.</p>
      </div>
    </div>
    <div id="slide2" class="carousel-item relative w-full">
      <img src="https://images.unsplash.com/photo-1595950653106-6c9ebd614d3a?auto=format&fit=crop&q=80&w=1000" class="w-full object-cover" />
      <div class="absolute left-5 right-5 top-1/2 flex -translate-y-1/2 transform justify-between">
        <a href="#slide1" class="btn btn-circle">❮</a>
        <a href="#slide3" class="btn btn-circle">❯</a>
      </div>
       <div class="absolute bottom-5 left-1/2 -translate-x-1/2 text-white bg-black/50 p-4 rounded-lg text-center">
        <h2 class="text-3xl font-bold">Performance Running</h2>
        <p>Engineered for speed and endurance.</p>
      </div>
    </div>
    <div id="slide3" class="carousel-item relative w-full">
      <img src="https://images.unsplash.com/photo-1525966222134-fcfa99b8ae77?auto=format&fit=crop&q=80&w=1000" class="w-full object-cover" />
      <div class="absolute left-5 right-5 top-1/2 flex -translate-y-1/2 transform justify-between">
        <a href="#slide2" class="btn btn-circle">❮</a>
        <a href="#slide1" class="btn btn-circle">❯</a>
      </div>
       <div class="absolute bottom-5 left-1/2 -translate-x-1/2 text-white bg-black/50 p-4 rounded-lg text-center">
        <h2 class="text-3xl font-bold">Classic Styles</h2>
        <p>Timeless designs for every occasion.</p>
      </div>
    </div>
  </div>
</template>

<style scoped>
</style>
