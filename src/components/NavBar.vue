<script setup>
// import { defineEmits } from 'vue'
import { gsap } from 'gsap'
import { ScrollToPlugin } from 'gsap/ScrollToPlugin'
const scrollTo = (select) => {
  gsap.registerPlugin(ScrollToPlugin)
  gsap.to(window, { duration: 1, scrollTo: { y: '#' + select, offsetY: 30 } })
}
</script>

<template>
  <nav ref="home" class="bg-[#141625]">
    <div
      class="w-11/12 h-auto px-3 sm:px-7 md:px-10 py-4 mx-auto flex justify-between items-center"
    >
      <div class="name text-white text-xl sm:text-3xl">
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
      <div class="dropdown dropdown-end block md:hidden">
        <div tabindex="0" role="button">
          <i class="fa-solid fa-bars text-3xl text-white"></i>
        </div>
        <ul
          tabindex="0"
          class="menu dropdown-content bg-white rounded-box z-[1] mt-3 w-56 p-2 top-10 shadow text-xl"
        >
          <li>
            <button
              @click="scrollTo('about')"
              class="btn bg-white border-none shadow-none justify-start text-xl font-normal hover:bg-[#3ABEF9] after:!hidden"
            >
              About
            </button>
          </li>
          <li>
            <button
              @click="scrollTo('projects')"
              class="btn bg-white border-none shadow-none justify-start text-xl font-normal hover:bg-[#3ABEF9] after:!hidden"
            >
              Projects
            </button>
          </li>
          <li>
            <button
              @click="scrollTo('contact')"
              class="btn bg-white border-none shadow-none justify-start text-xl font-normal hover:bg-[#3ABEF9] after:!hidden"
            >
              Contact
            </button>
          </li>
        </ul>
      </div>
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
</style>
