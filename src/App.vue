<script setup>
import { ref } from 'vue';
import { RouterView } from 'vue-router';
import preload from '@/components/PreLoad.vue';
import NavBar from '@/components/NavBar.vue';
import FooterView from '@/components/FooterView.vue';

const isLoading = ref(true);
setTimeout(function () {
  isLoading.value = false;
}, 1700);
</script>

<template>
  <div v-if="isLoading">
    <preload />
  </div>
  <div v-else>
    <NavBar />
    <RouterView />
    <FooterView />
  </div>
</template>

<style>
body {
  overflow-x: hidden;
}

.nav-item:after {
  content: '';
  position: absolute;
  bottom: -5px;
  left: 50%;
  height: 2px;
  width: 100%;
  transform: translateX(-50%) scaleX(0);
  background-color: #3abef9;
  transition: transform 0.3s ease-in-out;
}
.nav-item:hover:after {
  transform: translateX(-50%) scaleX(1);
}
</style>
