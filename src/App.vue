<script setup>
import { ref } from 'vue'
import { RouterView } from 'vue-router'
import preload from '@/components/PreLoad.vue'
import NavBar from '@/components/NavBar.vue'
import FooterView from '@/components/FooterView.vue'

const isLoading = ref(true)
setTimeout(function () {
  isLoading.value = false
}, 1700)
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
@import url('https://fonts.googleapis.com/css2?family=Inter:ital,opsz,wght@0,14..32,100..900;1,14..32,100..900&display=swap');

body {
  overflow-x: hidden;
}
</style>
