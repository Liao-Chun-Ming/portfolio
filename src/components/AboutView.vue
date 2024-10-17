<script setup>
import { ref, onMounted } from 'vue'
import AOS from 'aos'
import 'aos/dist/aos.css'
import html5 from '@/assets/html5.svg'
import css3 from '@/assets/css3.svg'
import javascript from '@/assets/javascript.svg'
import bootstrap from '@/assets/bootstrap.svg'
import scss from '@/assets/sass.svg'
import tailwind from '@/assets/tailwindcss.svg'
import vuejs from '@/assets/vuejs.svg'
import pinia from '@/assets/pinia.svg'
import python from '@/assets/python.svg'
import rstudio from '@/assets/rstudioide.svg'
import tableau from '@/assets/tableau.svg'
import git from '@/assets/git.svg'
import firebase from '@/assets/firebase.svg'
import codebg from '@/assets/codebg.jpeg'

const tools = [
  {
    category: 'basics',
    content: [
      {
        name: 'HTML5',
        img: html5
      },
      {
        name: 'CSS3',
        img: css3
      },
      {
        name: 'JavaScript',
        img: javascript
      }
    ]
  },
  {
    category: 'framework',
    content: [
      {
        name: 'Bootstrap',
        img: bootstrap
      },
      {
        name: 'SCSS',
        img: scss
      },
      {
        name: 'Tailwind',
        img: tailwind
      },
      {
        name: 'VueJS',
        img: vuejs
      },
      {
        name: 'Pinia',
        img: pinia
      }
    ]
  },
  {
    category: 'others',
    content: [
      {
        name: 'Git',
        img: git
      },
      {
        name: 'Firebase',
        img: firebase
      },
      {
        name: 'Python',
        img: python
      },
      {
        name: 'Rstudio',
        img: rstudio
      },
      {
        name: 'Tableau',
        img: tableau
      }
    ]
  }
]
const mobile = ref(null)
const checkScreen = () => {
  const windowWidth = window.innerWidth
  if (windowWidth < 768) {
    mobile.value = true
    return
  }
  mobile.value = false
}
onMounted(() => {
  checkScreen()
  window.addEventListener('resize', checkScreen)
  AOS.init()
})
</script>

<template>
  <section class="mb-10" id="about">
    <h2 class="text-4xl font-semibold text-center pb-8">About</h2>
    <div class="card xl:card-side gap-10">
      <figure>
        <img :src="codebg" alt="Album" class="rounded-full" />
      </figure>
      <div class="card-body">
        <h3 class="card-title text-3xl mb-2">Develop Tool</h3>
        <div class="flex flex-col md:flex-row items-center md:items-start gap-8">
          <div
            v-for="(item, index) in tools"
            :key="index"
            class="w-full text-xl flex flex-1 flex-col items-center flex-wrap"
          >
            <h4 class="uppercase text-center mb-2">{{ item.category }}</h4>
            <hr class="w-full h-1 mx-auto rounded-md bg-black" />
            <div class="w-full flex flex-row md:flex-col gap-4 flex-wrap py-4">
              <div v-for="(tool, index) in item.content" :key="index" class="flex items-center">
                <div class="flex items-center justify-center gap-3">
                  <img :src="tool.img" alt="" class="w-10" />
                  <p v-if="!mobile">{{ tool.name }}</p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <hr class="w-full h-0.5 bg-gray-300 my-10" />
    <div class="flex items-center">
      <div class="flex flex-col flex-1 justify-center gap-4">
        <h3 class="text-3xl font-semibold mb-2">Education & Experience</h3>
        <ol class="relative border-s border-gray-700 ml-5">
          <li class="mb-10 ms-8">
            <span
              class="absolute flex items-center justify-center w-6 h-6 bg-blue-100 rounded-full -start-3 ring-8 ring-white"
            >
              <i class="fa-solid fa-briefcase text-sm"></i>
            </span>
            <h4
              class="flex flex-col sm:flex-row items-start mb-1 text-lg font-semibold text-gray-900"
            >
              <span class="order-2 sm:order-1"
                >Figma UI/UX and Vue.js Front-End Training Course</span
              >
              <span
                class="order-1 sm:order-2 bg-blue-100 text-blue-800 text-sm font-medium sm:ml-2 px-2.5 py-0.5 rounded"
                >Latest
              </span>
            </h4>
            <time class="block mb-2 text-sm font-normal leading-none text-[#0f4c81]"
              >From April 2024 to August 2024</time
            >
            <div class="w-2/3">
              <p class="mb-4 text-base font-normal text-gray-500">
                By participating in the four-month front-end course training, I mastered html, css,
                javascript, and learned front-end frameworks such as Bootstrap, TailwindCSS, and
                Vue.js. In terms of API connection, fetch or axios are used to achieve asynchronous
                data exchange with the server.When using third-party packages, I also have the
                ability to self-study and read official documents.
              </p>
            </div>
          </li>
          <li class="mb-10 ms-8">
            <span
              class="absolute flex items-center justify-center w-6 h-6 bg-blue-100 rounded-full -start-3 ring-8 ring-white"
            >
              <i class="fa-solid fa-briefcase text-sm"></i>
            </span>
            <h4 class="flex items-center mb-1 text-lg font-semibold text-gray-900">
              Research Assistant at Tunghai University
            </h4>
            <time class="block mb-2 text-sm font-normal leading-none text-[#0f4c81]"
              >From July 2022 to April 2024</time
            >
            <div class="mb-4 text-base font-normal text-gray-500">
              <ul class="custom-list flex flex-col gap-1">
                <li>&nbsp;Institutional Research and Data Management</li>
                <li>&nbsp;Analysis of Internal Unit Issues</li>
                <li>&nbsp;Tableau Dashboard Creation and Maintenance</li>
              </ul>
            </div>
          </li>
          <li class="mb-10 ms-8">
            <span
              class="absolute flex items-center justify-center w-6 h-6 bg-blue-100 rounded-full -start-3 ring-8 ring-white"
            >
              <i class="fa-solid fa-school text-sm"></i>
            </span>
            <h4 class="mb-1 text-lg font-semibold text-gray-900">
              Institute of Statistics, National Chung Hsing University
            </h4>
            <time class="block mb-2 text-sm font-normal leading-none text-[#0f4c81]"
              >From September 2019 to July 2021</time
            >
            <div class="w-2/3 mb-4">
              <p class="text-base font-normal text-gray-500">
                Thesis:Using two-stage regression model to estimate air pollutants impact on the
                number of AURTI in different age groups: Take Taipei area as an example
              </p>
            </div>
          </li>
          <li class="mb-10 ms-8">
            <span
              class="absolute flex items-center justify-center w-6 h-6 bg-blue-100 rounded-full -start-3 ring-8 ring-white"
            >
              <i class="fa-solid fa-school text-sm"></i>
            </span>
            <h4 class="mb-1 text-lg font-semibold text-gray-900">
              Department of Applied Mathematics,National PingTung University
            </h4>
            <time class="block mb-2 text-sm font-normal leading-none text-[#0f4c81]"
              >From September 2015 to June 2019</time
            >
            <p class="text-base font-normal text-gray-500"></p>
          </li>
        </ol>
      </div>
      <!-- <figure>
        <img :src="codebg" alt="Album" class="h-full object-cover" />
      </figure> -->
    </div>
    <hr class="w-full h-[2px] bg-gray-300 my-10" />
  </section>
</template>
<style scoped>
.custom-list {
  list-style-type: none;
  list-style-position: inside;
}
.custom-list li::marker {
  content: '➤';
  color: rgb(255, 133, 4);
}
</style>
