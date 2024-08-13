<script setup>
import { ref, onMounted, onBeforeUnmount } from 'vue'
import AboutView from '../components/AboutView.vue'
import ProjectView from '../components/ProjectView.vue'
import ContactView from '../components/ContactView.vue'
import lottie from 'lottie-web'

const isVisible = ref(false)
const goTopRef = ref(null)
const scrollFunction = () => {
  isVisible.value = window.scrollY > 500
}

const goTop = () => {
  window.scrollTo({
    top: 0,
    behavior: 'smooth'
  })
}

const loadAnimation = (goTopRef) => {
  lottie.loadAnimation({
    container: goTopRef.value,
    renderer: 'svg',
    loop: true,
    autoplay: true,
    path: 'arrowUp.json'
  })
}

onMounted(() => {
  loadAnimation(goTopRef)
  window.addEventListener('scroll', scrollFunction)
})

onBeforeUnmount(() => {
  window.removeEventListener('scroll', scrollFunction)
})
</script>

<template>
  <main class="text-xl bg-[#f5f5f5]">
    <div class="w-5/6 m-auto py-8">
      <AboutView ref="about" />
      <ProjectView ref="projects" />
      <ContactView ref="contact" />
    </div>
    <button
      type="button"
      ref="goTopRef"
      @click="goTop"
      class="w-14 h-14 bg-black rounded-full sticky bottom-0 -translate-y-1/2 transition-all linear duration-500"
      :class="isVisible ? 'left-[95%] -translate-x-[10%]' : 'left-full translate-x-full'"
    ></button>
  </main>
</template>
