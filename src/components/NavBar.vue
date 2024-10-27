<script setup>
import { ref, onMounted } from 'vue'
import { gsap } from 'gsap'
import { ScrollToPlugin } from 'gsap/ScrollToPlugin'

const menuToggle = ref(null)
const menuWrap = ref(null)

const toggleMenu = () => {
  menuToggle.value = !menuToggle.value
}

const clickCheck = (e) => {
  if (e.target === menuWrap.value) toggleMenu()
}
const checkScreen = () => {
  const width = window.innerWidth
  if (width > 767) {
    menuToggle.value = false
  }
}

window.addEventListener('resize', checkScreen)

const scrollTo = (select) => {
  gsap.registerPlugin(ScrollToPlugin)
  gsap.to(window, { duration: 1, scrollTo: { y: '#' + select, offsetY: 30 } })
  toggleMenu()
}

onMounted(() => {
  checkScreen()
})
</script>

<template>
  <nav ref="home" class="bg-[#141625]">
    <div class="relative w-full px-3 sm:px-14 md:px-24 py-4 flex items-center">
      <div class="flex-1 text-white text-xl sm:text-3xl">
        <p>From Data To Code</p>
      </div>
      <div class="hidden md:block">
        <ul class="flex text-xl gap-4 text-white">
          <li>
            <button
              @click="scrollTo('about')"
              class="relative inline-block no-underline hover:text-[#3ABEF9]"
            >
              About
            </button>
          </li>
          <li>
            <button
              @click="scrollTo('projects')"
              class="relative inline-block no-underline hover:text-[#3ABEF9]"
            >
              Projects
            </button>
          </li>
          <li>
            <button
              @click="scrollTo('contact')"
              class="relative inline-block no-underline hover:text-[#3ABEF9]"
            >
              Contact
            </button>
          </li>
        </ul>
      </div>
      <div @click="toggleMenu" tabindex="0" role="button" class="block md:hidden">
        <i v-if="!menuToggle" class="fa-solid fa-bars text-3xl text-white"></i>
        <i v-else class="fa-solid fa-x text-3xl text-white"></i>
      </div>
      <transition name="slide-down">
        <div
          v-if="menuToggle"
          ref="menuWrap"
          @click="clickCheck"
          class="absolute right-0 top-[68px] h-screen w-full z-10 block md:hidden"
        >
          <ul
            class="bg-[#141625] flex flex-col items-center text-xl gap-4 text-white py-4 shadow-[0_10px_6px_-1px_rgba(0,0,0,0.2),0_2px_4px_-1px_rgba(0,0,0,0.06)]"
          >
            <li>
              <button
                @click="scrollTo('about')"
                class="relative inline-block no-underline hover:text-[#3ABEF9]"
              >
                About
              </button>
            </li>
            <li>
              <button
                @click="scrollTo('projects')"
                class="relative inline-block no-underline hover:text-[#3ABEF9]"
              >
                Projects
              </button>
            </li>
            <li>
              <button
                @click="scrollTo('contact')"
                class="relative inline-block no-underline hover:text-[#3ABEF9]"
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

.slide-down-enter-active,
.slide-down-leave-active {
  transition: all 0.7s ease;
}

.slide-down-enter-from,
.slide-down-leave-to {
  transform: translateX(100%);
}
</style>
