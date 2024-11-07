<script setup>
import { ref, onMounted } from 'vue'
import { gsap } from 'gsap'
const title1 = ref(null)
const paraOne = ref(null)
const title2 = ref(null)
const paraTwo = ref(null)
onMounted(() => {
  const tl = gsap.timeline({ delay: 0.5, pause: true })
  tl.from(title1.value, { x: 50, autoAlpha: 0, duration: 0.7 })
  tl.from(paraOne.value, { x: -50, autoAlpha: 0, duration: 0.7 })
  tl.from(title2.value, { x: 50, autoAlpha: 0, duration: 0.7 })
  tl.from(paraTwo.value, { x: -50, autoAlpha: 0, duration: 0.7 })
  tl.play()
})
</script>

<template>
  <div class="w-5/6 xl:w-4/6 m-auto py-14">
    <div
      class="card lg:card-side bg-[#ffffff1a] border-[#d3d3d333] backdrop-blur-md p-4 sm:p-6 flex justify-center items-center shadow-[5px_5px_20px_rgba(255,255,255,0.2)]"
    >
      <div class="card-body w-full lg:w-3/5 xl:w-2/3 p-4 sm:px-8 py-20 gap-5">
        <h2
          ref="title1"
          class="card-title text-2xl sm:text-4xl my-2 bg-gradient-to-r from-[#36D1DC] to-[#5B86E5] text-transparent bg-clip-text"
        >
          On the way to the front end...
        </h2>
        <p ref="paraOne" class="text-base text-white leading-9 sm:text-xl sm:leading-7 indent-10">
          Hello, My name is Chun-Ming,Liao. I'm a front-end development engineer. I learn through
          self-study and participation in training. I'm passionate about making websites that allow
          users to interact well.In the future,I will also keep learning.
        </p>
        <h2
          ref="title2"
          class="card-title justify-end text-2xl sm:text-4xl my-2 bg-gradient-to-r from-[#fc00ff] to-[#00dbde] text-transparent bg-clip-text"
        >
          ...Practice makes perfect
        </h2>
        <p ref="paraTwo" class="text-base text-white leading-9 sm:text-xl sm:leading-7 indent-10">
          I mainly use Vue.js to develop web pages, and use the Tailwind CSS framework、Pinia to
          manage states、Git for version control and Firebase for store the data.I will continue to
          learn in the future.
        </p>
      </div>
      <figure class="w-4/6 lg:w-2/5 xl:w-1/3 rounded-xl">
        <img src="/avatar.jpg" alt="Avatar" class="w-full rounded-xl" />
      </figure>
    </div>
  </div>
</template>
