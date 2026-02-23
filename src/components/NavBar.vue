<script setup>
import { onMounted, onUnmounted } from 'vue';
import { useCartStore } from '../stores/cartStore';

const cartStore = useCartStore();

onMounted(() => {
  console.log("NavBar mounted");
});

onUnmounted(() => {
  console.log("NavBar unmounted");
});
</script>

<template>
  <div class="navbar bg-primary text-primary-content shadow-lg sticky top-0 z-50">
    <div class="container mx-auto">
      <div class="flex-1">
        <router-link to="/" class="btn btn-ghost text-xl">Footwear Store</router-link>
      </div>
      <div class="flex-none">
        <ul class="menu menu-horizontal px-1">
          <li><router-link to="/">Home</router-link></li>
          <li>
            <router-link to="/cart">
              Cart
              <div v-if="cartStore.totalItems > 0" class="badge badge-secondary badge-sm">{{ cartStore.totalItems }}</div>
            </router-link>
          </li>
          <li><router-link to="/about">About</router-link></li>
        </ul>
      </div>
    </div>
  </div>
</template>

<style scoped>
.router-link-active {
  font-weight: bold;
  text-decoration: underline;
}
</style>
