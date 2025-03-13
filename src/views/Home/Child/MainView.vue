<script setup>
import { ref, onMounted } from 'vue';
import AboutView from '@/components/AboutView.vue';
import ProjectView from '@/components/ProjectView.vue';
import ContactView from '@/components/ContactView.vue';
import lottie from 'lottie-web';

const isVisible = ref(false);
const goTopRef = ref(null);

onMounted(() => {
  loadAnimation(goTopRef);
  window.addEventListener('scroll', scrollFunction);
});

const scrollFunction = () => {
  isVisible.value = window.scrollY > 500;
};

const goTop = () => {
  window.scrollTo({
    top: 0,
    behavior: 'smooth'
  });
};

const loadAnimation = (goTopRef) => {
  lottie.loadAnimation({
    container: goTopRef.value,
    renderer: 'svg',
    loop: true,
    autoplay: true,
    path: 'arrowUp.json'
  });
};
</script>

<template>
  <main class="bg-[#f5f5f5]">
    <div class="w-5/6 m-auto py-8">
      <AboutView />
      <ProjectView />
      <ContactView />
    </div>
    <button
      type="button"
      ref="goTopRef"
      @click="goTop"
      class="w-14 h-14 bg-black rounded-full sticky bottom-0 -translate-y-1/2 transition-all linear duration-500 shadow-[0_5px_29px_5px_rgba(0,0,0,0.3)] cursor-pointer"
      :class="isVisible ? 'left-[95%] -translate-x-[10%]' : 'left-full translate-x-full'"
    ></button>
  </main>
</template>
