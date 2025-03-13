<script setup>
import { ref, onMounted, computed } from 'vue';
import { gsap } from 'gsap';
import { ScrollToPlugin } from 'gsap/ScrollToPlugin';

const menuToggle = ref(null);
const menuWrap = ref(null);
const windowWidth = ref(null);

const isWideScreen = computed(() => windowWidth.value > 1023);

onMounted(() => {
  checkScreen();
});

const toggleMenu = () => {
  menuToggle.value = !menuToggle.value;
};

const clickCheck = (e) => {
  if (e.target === menuWrap.value) toggleMenu();
};

const checkScreen = () => {
  windowWidth.value = window.innerWidth;
  if (isWideScreen.value) {
    menuToggle.value = false;
  }
};

window.addEventListener('resize', checkScreen);

const scrollTo = (select) => {
  gsap.registerPlugin(ScrollToPlugin);
  gsap.to(window, { duration: 1, scrollTo: { y: '#' + select, offsetY: 30 } });
  if (!isWideScreen.value) menuToggle.value = false;
};
</script>

<template>
  <nav ref="home" class="bg-[#141625]">
    <div class="relative w-full px-4 sm:px-14 lg:px-24 py-4 flex items-center">
      <div class="flex-1 text-white text-xl sm:text-3xl">
        <p>From Data To Code</p>
      </div>
      <div class="hidden lg:block">
        <ul class="flex text-xl gap-4 text-white">
          <li>
            <button
              type="button"
              @click="scrollTo('about')"
              class="nav-item relative inline-block no-underline hover:text-[#3ABEF9] cursor-pointer"
            >
              About
            </button>
          </li>
          <li>
            <button
              type="button"
              @click="scrollTo('projects')"
              class="nav-item relative inline-block no-underline hover:text-[#3ABEF9] cursor-pointer"
            >
              Projects
            </button>
          </li>
          <li>
            <button
              type="button"
              @click="scrollTo('contact')"
              class="nav-item relative inline-block no-underline hover:text-[#3ABEF9] cursor-pointer"
            >
              Contact
            </button>
          </li>
        </ul>
      </div>
      <div @click="toggleMenu" tabindex="0" role="button" class="block lg:hidden cursor-pointer">
        <i v-if="!menuToggle" class="fa-solid fa-bars text-3xl text-white"></i>
        <i v-else class="fa-solid fa-x text-3xl text-white"></i>
      </div>
      <transition name="slide-down">
        <div
          v-if="menuToggle"
          ref="menuWrap"
          @click="clickCheck"
          class="absolute left-0 top-[68px] h-dvh w-full z-10 block lg:hidden"
        >
          <ul
            class="bg-[#141625] flex flex-col items-center text-xl gap-4 text-white p-4 shadow-[0_10px_6px_-1px_rgba(255,255,255,0.05),0_2px_4px_-1px_rgba(255,255,255,0.05)]"
          >
            <li>
              <button
                type="button"
                @click="scrollTo('about')"
                class="nav-item relative inline-block no-underline hover:text-[#3ABEF9] cursor-pointer"
              >
                About
              </button>
            </li>
            <li>
              <button
                type="button"
                @click="scrollTo('projects')"
                class="nav-item relative inline-block no-underline hover:text-[#3ABEF9] cursor-pointer"
              >
                Projects
              </button>
            </li>
            <li>
              <button
                type="button"
                @click="scrollTo('contact')"
                class="nav-item relative inline-block no-underline hover:text-[#3ABEF9] cursor-pointer"
              >
                Contact
              </button>
            </li>
          </ul>
        </div>
      </transition>
    </div>
  </nav>
</template>

<style scoped>
.slide-down-enter-active,
.slide-down-leave-active {
  transition: all 0.7s ease;
}

.slide-down-enter-from,
.slide-down-leave-to {
  transform: translateX(-100%);
}
</style>
