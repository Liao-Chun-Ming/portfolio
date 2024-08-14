<script setup>
import { ref, onMounted, defineEmits } from 'vue'
const year = ref('')

const getYear = () => {
  const now = new Date()
  year.value = now.getFullYear()
}
const emit = defineEmits(['scroll-to'])

const scrollTo = (elementId) => {
  emit('scroll-to', elementId)
}
onMounted(() => {
  getYear()
})
</script>

<template>
  <footer class="footer footer-center bg-black text-base-content rounded p-10">
    <div class="flex flex-col sm:flex-row justify-between gap-4 text-xl">
      <button
        @click="scrollTo('about')"
        class="relative inline-block no-underline text-white hover:text-[#3ABEF9]"
      >
        About
      </button>
      <button
        @click="scrollTo('projects')"
        class="relative inline-block no-underline text-white hover:text-[#3ABEF9]"
      >
        Projects
      </button>
      <button
        @click="scrollTo('contact')"
        class="relative inline-block no-underline text-white hover:text-[#3ABEF9]"
      >
        Contact
      </button>
    </div>
    <aside>
      <p class="text-white">Copyright © {{ year }}- All right reserved</p>
    </aside>
  </footer>
</template>

<style scoped>
button:after {
  background: transparent;
  bottom: 0;
  content: '';
  display: block;
  height: 2px;
  left: 50%;
  position: absolute;
  background: #3abef9;
  transition: width 0.3s ease 0s, left 0.3s ease 0s;
  width: 0;
}
button:hover:after {
  width: 100%;
  left: 0;
}
</style>
