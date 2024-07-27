<script setup>
import { ref, onMounted } from 'vue'
import { gsap } from 'gsap'
const title1 = ref(null)
const paraOne = ref(null)
const title2 = ref(null)
const paraTwo = ref(null)
onMounted(() => {
  console.log(paraTwo.value)
  const tl = gsap.timeline({ delay: 0.5, pause: true })
  tl.from(title1.value, { y: '+200', autoAlpha: 0, duration: 0.7 })
  tl.from(paraOne.value, { y: '+200', autoAlpha: 0, duration: 0.7 })
  tl.from(title2.value, { y: '+200', autoAlpha: 0, duration: 0.7 })
  tl.from(paraTwo.value, { y: '+200', autoAlpha: 0, duration: 0.7 })
  tl.play()
})
</script>

<template>
  <header class="bg-[url('/background.jpg')] bg-cover bg-center">
    <div class="w-5/6 xl:w-4/6 m-auto py-14">
      <div
        class="card lg:card-side bg-white shadow-2xl p-4 sm:p-6 flex justify-center items-center"
      >
        <div class="card-body w-full lg:w-3/5 xl:w-2/3 p-4 sm:p-8 gap-5">
          <h2
            ref="title1"
            class="card-title text-2xl sm:text-4xl my-2 bg-gradient-to-r from-[#36D1DC] to-[#5B86E5] text-transparent bg-clip-text"
          >
            On the way to the front end...
          </h2>
          <p
            ref="paraOne"
            class="text-base leading-9 sm:text-xl sm:leading-9 indent-10 text-justify tracking-normal"
          >
            你好
            ，我是廖春茗，原本在東海大學當研究助理，主要負責校務資料分析、Tableau儀表板製作與維護。偶然接觸到了前端開發，隨著對這個領域的深入了解，我被前端開發的創造性和實踐性吸引，決定轉職成為一名前端開發工程師。
          </p>
          <h2
            ref="title2"
            class="card-title justify-end text-2xl sm:text-4xl my-2 bg-gradient-to-r from-[#fc00ff] to-[#00dbde] text-transparent bg-clip-text"
          >
            ...Practice makes perfect
          </h2>
          <p
            ref="paraTwo"
            class="text-base leading-9 sm:text-xl sm:leading-9 indent-10 text-justify tracking-normal"
          >
            我利用自學和參加培訓，有系統地學習了HTML、CSS和JavaScript，並使用了多個前端框架，如Bootstrap、Tailwind和Vue.js。我透過不斷地練習提升自己的技能，並將所學應用到實際項目中，從中累積開發經驗。
          </p>
        </div>
        <figure class="w-4/6 lg:w-2/5 xl:w-1/3 rounded-xl">
          <img src="/avatar.jpg" alt="Avatar" class="w-full rounded-xl" />
        </figure>
      </div>
    </div>
  </header>
</template>
