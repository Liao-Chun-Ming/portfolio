<script setup>
import { onMounted } from 'vue'
import AOS from 'aos'
import 'aos/dist/aos.css'
onMounted(() => {
  AOS.init()
})
</script>

<template>
  <section id="projects">
    <div class="project-card w-full bg-[#1f1f1f] rounded-xl px-6 py-12 lg:p-12">
      <h2 class="text-white text-4xl font-semibold text-start mb-5">Project Showcase</h2>
      <a
        href="https://github.com/monky6503?tab=repositories"
        target="_blank"
        class="relative btn gitbtn border-none bg-white text-black text-sm rounded-full px-3 py-2 mb-5 inline-flex items-center justify-center gap-2 z-10"
      >
        <i class="fa-brands fa-github text-2xl"></i>
        Explore my projects
        <i class="fa-solid fa-arrow-right mx-2"></i
      ></a>
      <div
        class="w-full grid grid-cols-1 lg:grid-cols-2 3xl:grid-cols-4 justify-center gap-10 text-white"
      >
        <div
          class="px-5 py-8 bg-[#282828] border border-[#484848] rounded-2xl flex flex-col justify-between"
          data-aos="zoom-in"
        >
          <div>
            <i
              class="fa-solid fa-cloud p-3 text-2xl sm:text-4xl bg-[#303030] border border-[#606060] rounded-xl"
            ></i>
            <a
              href="https://monky6503.github.io/weather-Vue-/"
              target="_blank"
              class="inline-block md:block ml-3 md:ml-0 mt-4 mb-2 text-white text-xl font-semibold"
              >Weather Card</a
            >
            <p class="text-[#fff] text-sm sm:text-base py-3 md:py-4 indent-8">
              The weather card uses Fetch to obtain and organize weather forecast data from the
              Central Meteorological Administration, and displays the current 12-hour weather
              forecast for each county and city on the web page. Users can switch to displaying the
              weather in different regions by clicking the button above.
            </p>
          </div>
          <div class="flex flex-wrap items-center gap-2 py-1">
            <div class="badge badge-outline text-[#38BDF8] text-xs">Tailwind</div>
            <div class="badge badge-outline text-[#42B883] text-xs">Vue</div>
          </div>
        </div>
        <div
          class="px-5 py-8 bg-[#282828] border border-[#484848] rounded-2xl flex flex-col justify-between"
          data-aos="zoom-in"
        >
          <div>
            <i
              class="fa-solid fa-film p-3 text-2xl sm:text-4xl bg-[#303030] border border-[#606060] rounded-xl"
            ></i>
            <a
              href="https://monky6503.github.io/movie-Vue-/"
              target="_blank"
              class="inline-block md:block ml-3 md:ml-0 mt-4 mb-2 text-white text-xl font-semibold"
              >Movies Search</a
            >
            <p class="text-[#fff] text-sm sm:text-base py-3 md:py-4 indent-8">
              In the movie search project, I used OMDB API and Vue.js. Users can enter the movie
              name and release year to search, and then they can find relevant movie information
              (release date, director, screenwriter, actors, etc.), and they can also add Add your
              favorite movies to My Favorites and you can introduce your favorite movies to others
              at any time.
            </p>
          </div>
          <div class="flex flex-wrap items-center gap-2 py-1">
            <div class="badge badge-outline text-[#38BDF8] text-xs">Tailwind</div>
            <div class="badge badge-outline text-[#42B883] text-xs">Vue</div>
          </div>
        </div>
        <div
          class="px-5 py-8 bg-[#282828] border border-[#484848] rounded-2xl flex flex-col justify-between"
          data-aos="zoom-in"
        >
          <div>
            <i
              class="fa-solid fa-cart-shopping p-3 text-2xl sm:text-4xl bg-[#303030] border border-[#606060] rounded-xl"
            ></i>
            <a
              href="https://monky6503.github.io/Shopping-Cart/"
              target="_blank"
              class="inline-block md:block ml-3 md:ml-0 mt-4 mb-2 text-white text-xl font-semibold"
              >Shopping Cart</a
            >
            <p class="text-[#fff] text-sm sm:text-base py-3 md:py-4 indent-8">
              This is a shopping website with APPLE as the theme, including a login page, homepage
              and shopping cart page. Mainly written using bootsrap with SCSS and vanilla
              javaScript, the data is stored in the browser through localStorage so that it can be
              brought to other pages to achieve the effect of adding items to the shopping cart.
            </p>
          </div>
          <div class="flex flex-wrap items-center gap-2 py-1">
            <div class="badge badge-outline text-[#b57dff] text-xs">Bootstrap</div>
            <div class="badge badge-outline text-[#f84600] text-xs">SCSS</div>
            <div class="badge badge-outline text-[#F8D900] text-xs">JavaScript</div>
          </div>
        </div>
        <div
          class="px-5 py-8 bg-[#282828] border border-[#484848] rounded-2xl flex flex-col justify-between"
          data-aos="zoom-in"
        >
          <div>
            <i
              class="fa-solid fa-palette p-3 text-2xl sm:text-4xl bg-[#303030] border border-[#606060] rounded-xl"
            ></i>
            <a
              href="https://monky6503.github.io/colorGame-Vue-/"
              target="_blank"
              class="inline-block md:block ml-3 md:ml-0 mt-4 mb-2 text-white text-xl"
              >Color Game</a
            >
            <p class="text-[#fff] text-sm sm:text-base py-3 md:py-4 indent-8">
              This is a game that challenges eye recognition. You have to click on the squares of
              different colors to advance to the next level. If you answer incorrectly, points will
              be deducted. The further you go to the later levels, the harder it will be to
              distinguish them.
            </p>
          </div>
          <div class="flex flex-wrap items-center gap-2 py-1">
            <div class="badge badge-outline text-[#38BDF8] text-xs">Tailwind</div>
            <div class="badge badge-outline text-[#42B883] text-xs">Vue</div>
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
.gitbtn:hover:after {
  left: 0;
  width: 100%;
}
</style>
