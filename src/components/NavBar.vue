<script setup>
import { defineEmits } from 'vue'

const emit = defineEmits(['scroll-to'])

const scrollTo = (elementId) => {
  emit('scroll-to', elementId)
}
</script>

<template>
  <nav
    class="w-11/12 h-auto px-3 sm:px-7 md:px-10 py-4 mx-auto flex justify-between items-center"
    ref="home"
  >
    <div class="name text-white text-xl sm:text-3xl">
      <p>From Data To Code</p>
    </div>
    <div class="hidden md:block">
      <ul class="flex text-xl gap-4">
        <li>
          <button @click="scrollTo('about')" class="relative inline-block no-underline text-white">
            About
          </button>
        </li>
        <li>
          <button
            @click="scrollTo('projects')"
            class="relative inline-block no-underline text-white"
          >
            Projects
          </button>
        </li>
        <li>
          <button
            @click="scrollTo('contact')"
            class="relative inline-block no-underline text-white"
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
        class="menu dropdown-content bg-base-100 rounded-box z-[1] mt-3 w-56 p-2 top-10 shadow text-xl"
      >
        <li><button @click="scrollTo('about')">About</button></li>
        <li><button @click="scrollTo('projects')">Projects</button></li>
        <li><button @click="scrollTo('contact')">Contact</button></li>
      </ul>
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
  background: #fff;
  transition: width 0.3s ease 0s, left 0.3s ease 0s;
  width: 0;
}
button:hover:after {
  width: 100%;
  left: 0;
}
</style>
