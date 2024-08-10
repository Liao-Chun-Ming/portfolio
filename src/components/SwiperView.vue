<script setup>
// Import Swiper Vue.js components
import { Swiper, SwiperSlide } from 'swiper/vue'

// Import Swiper styles
import 'swiper/css'

import 'swiper/css/pagination'
import 'swiper/css/navigation'

// import required modules
import { Pagination, Navigation } from 'swiper/modules'

const modules = [Pagination, Navigation]
</script>

<template>
  <swiper
    :slidesPerView="3"
    :spaceBetween="50"
    :navigation="{
      prevEl: '.swiper-button-prev',
      nextEl: '.swiper-button-next'
    }"
    :modules="modules"
    class="mySwiper w-full flex justify-center gap-10 text-white"
  >
    <swiper-slide>
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
            Central Meteorological Administration, and displays the current 12-hour weather forecast
            for each county and city on the web page. Users can switch to displaying the weather in
            different regions by clicking the button above.
          </p>
        </div>
        <div class="flex flex-wrap items-center gap-2 py-1">
          <div class="badge badge-outline text-[#38BDF8] text-xs">Tailwind</div>
          <div class="badge badge-outline text-[#42B883] text-xs">Vue</div>
        </div>
      </div>
    </swiper-slide>
    <swiper-slide
      ><div
        class="px-5 py-8 bg-[#282828] border border-[#484848] rounded-2xl flex flex-col justify-between"
      >
        <div>
          <i
            class="fa-solid fa-film p-3 text-2xl sm:text-4xl text-white bg-[#303030] border border-[#606060] rounded-xl"
          ></i>
          <a
            href="https://monky6503.github.io/movie-Vue-/"
            target="_blank"
            class="inline-block md:block ml-3 md:ml-0 mt-4 mb-2 text-white text-xl font-semibold"
            >Movies Search</a
          >
          <p class="text-[#fff] text-sm sm:text-base py-3 md:py-4 indent-8">
            In the movie search project, I used OMDB API and Vue.js. Users can enter the movie name
            and release year to search, and then they can find relevant movie information (release
            date, director, screenwriter, actors, etc.), and they can also add Add your favorite
            movies to My Favorites and you can introduce your favorite movies to others at any time.
          </p>
        </div>
        <div class="flex flex-wrap items-center gap-2 py-1">
          <div class="badge badge-outline text-[#38BDF8] text-xs">Tailwind</div>
          <div class="badge badge-outline text-[#42B883] text-xs">Vue</div>
        </div>
      </div>
    </swiper-slide>
    <swiper-slide
      ><div
        class="px-5 py-8 bg-[#282828] border border-[#484848] rounded-2xl flex flex-col justify-between"
      >
        <div>
          <i
            class="fa-solid fa-cart-shopping p-3 text-2xl sm:text-4xl text-white bg-[#303030] border border-[#606060] rounded-xl"
          ></i>
          <a
            href="https://monky6503.github.io/Shopping-Cart/"
            target="_blank"
            class="inline-block md:block ml-3 md:ml-0 mt-4 mb-2 text-white text-xl font-semibold"
            >Shopping Cart</a
          >
          <p class="text-[#fff] text-sm sm:text-base py-3 md:py-4 indent-8">
            This is a shopping website with APPLE as the theme, including a login page, homepage and
            shopping cart page. Mainly written using bootsrap with SCSS and vanilla javaScript, the
            data is stored in the browser through localStorage so that it can be brought to other
            pages to achieve the effect of adding items to the shopping cart.
          </p>
        </div>
        <div class="flex flex-wrap items-center gap-2 py-1">
          <div class="badge badge-outline text-[#b57dff] text-xs">Bootstrap</div>
          <div class="badge badge-outline text-[#f84600] text-xs">SCSS</div>
          <div class="badge badge-outline text-[#F8D900] text-xs">JavaScript</div>
        </div>
      </div>
    </swiper-slide>
    <swiper-slide>
      <div
        class="px-5 py-8 bg-[#282828] border border-[#484848] rounded-2xl flex flex-col justify-between"
      >
        <div>
          <i
            class="fa-solid fa-palette p-3 text-2xl sm:text-4xl text-white bg-[#303030] border border-[#606060] rounded-xl"
          ></i>
          <a
            href="https://monky6503.github.io/colorGame-Vue-/"
            target="_blank"
            class="inline-block md:block ml-3 md:ml-0 mt-4 mb-2 text-white text-xl font-semibold"
            >Color Game</a
          >
          <p class="text-[#fff] text-sm sm:text-base py-3 md:py-4 indent-8">
            This is a game that challenges eye recognition. You have to click on the squares of
            different colors to advance to the next level. If you answer incorrectly, points will be
            deducted. The further you go to the later levels, the harder it will be to distinguish
            them.
          </p>
        </div>
        <div class="flex flex-wrap items-center gap-2 py-1">
          <div class="badge badge-outline text-[#38BDF8] text-xs">Tailwind</div>
          <div class="badge badge-outline text-[#42B883] text-xs">Vue</div>
        </div>
      </div>
    </swiper-slide>

    <div ref="prevButton" class="swiper-button-prev"></div>
    <div ref="nextButton" class="swiper-button-next"></div>
  </swiper>
</template>
<style>
.swiper {
  width: 100%;
  height: 484px;
  padding: 0 40px;
}

.swiper-slide {
  text-align: center;
  font-size: 18px;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
}

.swiper-slide img {
  display: block;
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.swiper-button-next,
.swiper-button-prev {
  width: 50px;
  height: 50px;
  background-color: #606060;
  border-radius: 25px;
  color: white;
}
.swiper-button-next::after,
.swiper-button-prev::after {
  font-size: 30px;
  margin: auto;
  left: 0%;
}
.swiper-button-disabled {
  opacity: 0.5;
  pointer-events: none;
}
</style>
