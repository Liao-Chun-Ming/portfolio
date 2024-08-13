<script setup>
// import { defineEmits } from 'vue'

const emit = defineEmits(['scroll-to'])

const scrollTo = (elementId) => {
  emit('scroll-to', elementId)
}
</script>

<template>
  <nav ref="home" class="bg-gradient-to-b from-[#283048] to-[#434343]">
    <div
      class="w-11/12 h-auto px-3 sm:px-7 md:px-10 py-4 mx-auto flex justify-between items-center"
    >
      <div class="name text-white text-xl sm:text-3xl">
        <p>From Data To Code</p>
      </div>
      <div class="hidden md:block">
        <ul class="flex text-xl gap-4">
          <li>
            <button
              @click="scrollTo('about')"
              class="relative inline-block no-underline text-white hover:text-[#FF9A00]"
            >
              About
            </button>
          </li>
          <li>
            <button
              @click="scrollTo('projects')"
              class="relative inline-block no-underline text-white hover:text-[#FF9A00]"
            >
              Projects
            </button>
          </li>
          <li>
            <button
              @click="scrollTo('contact')"
              class="relative inline-block no-underline text-white hover:text-[#FF9A00]"
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
              class="btn bg-white border-none shadow-none justify-start text-xl font-normal hover:bg-[#ff9a00] after:!hidden"
            >
              About
            </button>
          </li>
          <li>
            <button
              @click="scrollTo('projects')"
              class="btn bg-white border-none shadow-none justify-start text-xl font-normal hover:bg-[#ff9a00] after:!hidden"
            >
              Projects
            </button>
          </li>
          <li>
            <button
              @click="scrollTo('contact')"
              class="btn bg-white border-none shadow-none justify-start text-xl font-normal hover:bg-[#ff9a00] after:!hidden"
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
  background: #ff9a00;
  transition: width 0.3s ease 0s, left 0.3s ease 0s;
  width: 0;
}
button:hover:after {
  width: 100%;
  left: 0;
}
</style>
