<script setup>
import { computed, onMounted, onUnmounted } from 'vue';
import { useRoute } from 'vue-router';
import { useProductStore } from '../stores/productStore';
import ProductDetails from '../components/ProductDetails.vue';
import ProductCard from '../components/ProductCard.vue';

const route = useRoute();
const productStore = useProductStore();
const productId = computed(() => route.params.id);

const product = computed(() => {
  return productStore.products?.find(p => String(p.id) === String(productId.value));
});

const relatedProducts = computed(() => {
  return productStore.products?.filter(p => String(p.id) !== String(productId.value));
});

onMounted(async () => {
  if (!productStore.products) {
    await productStore.fetchProducts();
  }
  console.log(`ProductView mounted for ID: ${productId.value}`);
});

onUnmounted(() => {
  console.log("ProductView unmounted");
});
</script>

<template>
  <div v-if="product" class="space-y-16">
    <ProductDetails :product="product" />
    
    <section>
      <div class="divider"></div>
      <h3 class="text-2xl font-bold mb-8">Related Products</h3>
      <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-8">
        <ProductCard 
          v-for="p in relatedProducts" 
          :key="p.id" 
          :product="p" 
        />
      </div>
    </section>
  </div>
  <div v-else-if="productStore.loading" class="flex justify-center py-20">
    <span class="loading loading-spinner loading-lg text-primary"></span>
  </div>
  <div v-else class="text-center py-20">
    <h2 class="text-3xl font-bold text-error">Product Not Found</h2>
    <router-link to="/" class="btn btn-primary mt-4">Back to Home</router-link>
  </div>
</template>

<style scoped>
/* Product specific styles */
</style>
