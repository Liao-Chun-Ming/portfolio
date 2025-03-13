<script setup>
import { ref, onMounted } from 'vue';
import AOS from 'aos';
import 'aos/dist/aos.css';
import VanillaTilt from 'vanilla-tilt';

const projectData = [
  {
    name: 'Fengyuan Bus Transportation',
    intro:
      'This is a bus transportation website, user can use it to search bus real-time dynamic information ,We also have recommended attractions for everyone, all of which can be reached via our buses.',
    url: 'https://liao-chun-ming.github.io/FengYuanBus/',
    icon: 'fa-bus',
    hashtag: [
      { package: 'Vue.js', color: '#42B883' },
      { package: 'Tailwind', color: '#38BDF8' },
      { package: 'Swiper', color: '#0180FF' },
      { package: 'GSAP', color: '#08E447' }
    ]
  },
  {
    name: 'Weather Card',
    intro:
      'The weather card uses Fetch to obtain and organize weather forecast data from the Central Meteorological Administration, and displays the current 12-hour weather forecast for each county and city on the web page. Users can switch to displaying the weather in different regions by clicking the button above.',
    url: 'https://liao-chun-ming.github.io/weather-Vue-/',
    icon: 'fa-cloud',
    hashtag: [
      { package: 'Vue.js', color: '#42B883' },
      { package: 'Tailwind', color: '#38BDF8' }
    ]
  },
  {
    name: 'Movie Search',
    intro:
      'In the movie search project, I used OMDB API and Vue.js. Users can enter the movie name and release year to search, and then they can find relevant movie information (release date, director, screenwriter, actors, etc.), and they can also add Add your favorite movies to My Favorites and you can introduce your favorite movies to others.',
    url: 'https://liao-chun-ming.github.io/movie-Vue-/',
    icon: 'fa-film',
    hashtag: [
      { package: 'Vue.js', color: '#42B883' },
      { package: 'Tailwind', color: '#38BDF8' }
    ]
  },
  {
    name: 'E-commerce',
    intro:
      'This is a shopping website with APPLE as the theme, including a login page, homepage and shopping cart page. Mainly written using bootsrap with SCSS and vanilla javaScript, the data is stored in the browser through localStorage so that it can be brought to other pages to achieve the effect of adding items to the shopping cart.',
    url: 'https://liao-chun-ming.github.io/Shopping-Cart/',
    icon: 'fa-cart-shopping',
    hashtag: [
      { package: 'JavaScript', color: '#F8D900' },
      { package: 'Bootstrap', color: '#b57dff' },
      { package: 'SCSS', color: '#f84600' }
    ]
  },
  {
    name: 'Color Game',
    intro:
      'This is a game that challenges eye recognition. You have to click on the squares of different colors to advance to the next level. If you answer incorrectly, points will be deducted. The further you go to the later levels, the harder it will be to distinguish them.',
    url: 'https://liao-chun-ming.github.io/colorGame-Vue-/',
    icon: 'fa-palette',
    hashtag: [
      { package: 'Vue.js', color: '#42B883' },
      { package: 'Tailwind', color: '#38BDF8' }
    ]
  },
  {
    name: 'Calendar',
    intro:
      'Calendar using firebase to store data, allowing users to perform CRUD operations on selected dates.',
    url: 'https://liao-chun-ming.github.io/Calendar/',
    icon: 'fa-calendar',
    hashtag: [
      { package: 'Vue.js', color: '#42B883' },
      { package: 'Tailwind', color: '#38BDF8' },
      { package: 'Firebase', color: '#DD2C00' }
    ]
  }
];
const cardElement = ref(null);

onMounted(() => {
  AOS.init();
  VanillaTilt.init(cardElement.value, {
    reverse: true,
    max: 15,
    speed: 900,
    glare: true,
    'max-glare': 0.3,
    easing: 'cubic-bezier(.03,.98,.52,.99)'
  });
});
</script>

<template>
  <section id="projects">
    <div class="project-card w-full bg-[#1f1f1f] rounded-xl px-6 py-12 lg:p-12">
      <h2 class="text-white text-4xl font-semibold text-start mb-5">Project Showcase</h2>
      <a
        href="https://github.com/Liao-Chun-Ming"
        target="_blank"
        class="relative btn gitbtn border-none bg-white text-black text-sm rounded-full px-3 py-2 mb-5 inline-flex items-center justify-center gap-2 z-10"
      >
        <i class="fa-brands fa-github text-2xl"></i>
        Explore my projects
        <i class="fa-solid fa-arrow-right mx-2"></i
      ></a>
      <div
        class="w-full grid grid-cols-1 lg:grid-cols-2 2xl:grid-cols-4 justify-center gap-10 text-white"
      >
        <div
          ref="cardElement"
          v-for="(item, index) in projectData"
          :key="index"
          class="px-5 py-8 bg-[#282828] border border-[#484848] rounded-2xl flex flex-col justify-between"
          data-aos="zoom-in"
        >
          <div>
            <i
              class="fa-solid p-3 text-2xl sm:text-4xl bg-[#303030] border border-[#606060] rounded-xl"
              :class="item.icon"
            ></i>
            <a
              :href="item.url"
              target="_blank"
              class="inline-block md:block ml-3 md:ml-0 mt-4 mb-2 text-xl text-white hover:text-[#ff8800] transition-all ease-in-out duration-300"
              >{{ item.name }}</a
            >
            <p class="text-[#fff] text-sm sm:text-base py-3 md:py-4 indent-8">
              {{ item.intro }}
            </p>
          </div>
          <div class="flex flex-wrap items-center gap-2 py-1">
            <div
              v-for="(pkg, index) in item.hashtag"
              :key="index"
              class="badge badge-outline text-xs"
              :style="`color:${pkg.color}`"
            >
              {{ pkg.package }}
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.gitbtn::after {
  position: absolute;
  content: '';
  width: 0;
  height: 100%;
  top: 0;
  left: 50%;
  z-index: -1;
  background-color: #3abef9;
  border-radius: 9999px;
  transition: all 0.3s ease;
}
.gitbtn:hover::after {
  left: 0;
  width: 100%;
}
</style>
