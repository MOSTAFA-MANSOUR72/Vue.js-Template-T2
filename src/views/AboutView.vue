<script setup>
import { onMounted, onUnmounted } from 'vue';

onMounted(() => {
  console.log("AboutView mounted");
});

onUnmounted(() => {
  console.log("AboutView unmounted");
});
</script>

<template>
  <div class="max-w-4xl mx-auto space-y-10 py-12 px-6 bg-base-100 rounded-3xl shadow-xl">
    <div class="text-center space-y-4">
      <h1 class="text-5xl font-extrabold text-primary">About Our Store</h1>
      <p class="text-xl text-base-content/70">The destination for premium footwear enthusiasts.</p>
    </div>
    
    <div class="divider"></div>
    
    <div class="prose prose-lg max-w-none text-base-content/80 text-justify">
      <p>
        Welcome to the Footwear Store, your premier destination for high-quality shoes that blend style, comfort, and performance. 
        Whether you're looking for the perfect pair of sneakers for your daily commute, rugged boots for outdoor adventures, 
        or high-performance running shoes to beat your personal records, we have carefully curated our collection to meet every need.
      </p>
      <p>
        Our mission is simple: to provide our customers with the best footwear on the market while ensuring an exceptional 
        shopping experience. We believe that the right pair of shoes can take you anywhere, and we are here to help you find yours.
      </p>
    </div>
    
    <div class="bg-base-200 p-8 rounded-2xl flex flex-col md:flex-row justify-between items-center gap-6">
      <div class="space-y-1">
        <h2 class="text-2xl font-bold">Project Details</h2>
        <p class="font-medium">Lab 2: Multi-Page Product SPA</p>
      </div>
      <div class="text-right">
        <p class="text-lg font-bold">Developer: Mostafa</p>
        <p class="text-primary font-semibold">ITI - Vue.js Course</p>
      </div>
    </div>
  </div>
</template>

<style scoped>
/* About specific styles */
</style>
