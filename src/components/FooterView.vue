<script setup>
import { ref, onMounted } from 'vue';
import { gsap } from 'gsap';
import { ScrollToPlugin } from 'gsap/ScrollToPlugin';

const year = ref('');

onMounted(() => {
  getYear();
});

const getYear = () => {
  const now = new Date();
  year.value = now.getFullYear();
};

const scrollTo = (select) => {
  gsap.registerPlugin(ScrollToPlugin);
  gsap.to(window, { duration: 1, scrollTo: { y: '#' + select, offsetY: 30 } });
};
</script>

<template>
  <footer class="footer footer-horizontal footer-center bg-black text-base-content rounded-sm p-4">
    <div class="flex flex-col sm:flex-row justify-between gap-4 text-xl">
      <button
        type="button"
        @click="scrollTo('about')"
        class="nav-item relative inline-block no-underline text-white hover:text-[#3ABEF9] cursor-pointer"
      >
        About
      </button>
      <button
        type="button"
        @click="scrollTo('projects')"
        class="nav-item relative inline-block no-underline text-white hover:text-[#3ABEF9] cursor-pointer"
      >
        Projects
      </button>
      <button
        type="button"
        @click="scrollTo('contact')"
        class="nav-item relative inline-block no-underline text-white hover:text-[#3ABEF9] cursor-pointer"
      >
        Contact
      </button>
    </div>
    <aside>
      <p class="text-white">Copyright © {{ year }} ChunMing - All right reserved</p>
    </aside>
  </footer>
</template>
