<script>
  import AOS from 'aos'
  import 'aos/dist/aos.css'
  export default{
    data(){
      return{

      }
    },
    mounted(){
      AOS.init()
    }
  }
</script>

<template>
  <section id="projects">
    <div class="project-card w-full bg-[#1f1f1f] rounded-xl px-6 py-12 lg:p-12">
      <h2 class="text-white text-4xl font-semibold text-start mb-5">Project Showcase</h2>
      <a href="https://github.com/monky6503?tab=repositories" target="_blank"
        class="bg-white text-black text-sm rounded-full px-3 py-2 mb-5 inline-flex items-center justify-center gap-2 hover:bg-[#e2e2e2] active:bg-[#aeaeae]">
        <i class="fa-brands fa-github text-2xl"></i>
        Explore my projects
        <i class="fa-solid fa-arrow-right mx-2"></i></a>
      <div class="w-full grid grid-cols-1 md:grid-cols-2 xl:grid-cols-4 justify-center gap-10 text-white ">
        <div class="px-5 py-8 bg-[#282828] border border-[#484848] rounded-2xl flex flex-col justify-between"
          data-aos="zoom-in">
          <div>
            <i
              class="fa-solid fa-cloud p-3 text-2xl sm:text-4xl bg-[#303030] border border-[#606060] rounded-xl"></i>
            <a href="https://monky6503.github.io/weather-Vue-/" target="_blank"
              class="inline-block md:block ml-3 md:ml-0 mt-4 mb-2 text-white text-xl">Weather Card</a>
            <p class="text-[#fff] text-sm sm:text-base py-3 md:py-4 indent-8">
              天氣卡使用 Fetch 去獲取中央氣氣署的天氣預報資料並加以整理，並展示各縣市目前12小時內的天氣預報在網頁上，使用者點選上方按鈕則可以切換顯示不同地區的天氣。
            </p>
          </div>
          <div class="flex flex-wrap items-center gap-2 py-1">
            <div class="badge badge-outline text-[#38BDF8] text-xs">Tailwind</div>
            <div class="badge badge-outline text-[#42B883] text-xs">Vue</div>
          </div>
        </div>
        <div class="px-5 py-8 bg-[#282828] border border-[#484848] rounded-2xl flex flex-col justify-between"
          data-aos="zoom-in">
          <div>
            <i
              class="fa-solid fa-film  p-3 text-2xl sm:text-4xl bg-[#303030] border border-[#606060] rounded-xl"></i>
            <a href="https://monky6503.github.io/movie-Vue-/" target="_blank"
              class="inline-block md:block ml-3 md:ml-0 mt-4 mb-2 text-white text-xl">Movies Search</a>
            <p class="text-[#fff] text-sm sm:text-base py-3 md:py-4 indent-8">
              電影搜尋的項目中，我運用了 OMDB API 和 Vue.js
              ，使用者可以輸入電影名稱及發行年份來搜尋，即可找到相關的電影資訊（上映日期、導演、編劇、演員等），還可以將喜歡的電影加入我的最愛，隨時都可以向別人介紹自己喜歡的電影。
            </p>
          </div>
          <div class="flex flex-wrap items-center gap-2 py-1">
            <div class="badge badge-outline text-[#38BDF8] text-xs">Tailwind</div>
            <div class="badge badge-outline text-[#42B883] text-xs">Vue</div>
          </div>
        </div>
        <div class="px-5 py-8 bg-[#282828] border border-[#484848] rounded-2xl flex flex-col justify-between"
          data-aos="zoom-in">
          <div>
            <i
              class="fa-solid fa-cart-shopping p-3 text-2xl sm:text-4xl bg-[#303030] border border-[#606060] rounded-xl"></i>
            <a href="https://monky6503.github.io/Shopping-Cart/" target="_blank"
              class="inline-block md:block ml-3 md:ml-0 mt-4 mb-2 text-white text-xl">Shopping Cart</a>
            <p class="text-[#fff] text-sm sm:text-base py-3 md:py-4 indent-8">
              這是一個用APPLE當主題的購物網站，內容包含登入頁面、首頁及購物車頁面。主要使用 bootsrap 搭配 SCSS 和原生
              javaScript撰寫，透過localStorage將資料儲存在瀏覽器上以便帶到其他頁面，來達成將物品到入到購物車的效果。
            </p>
          </div>
          <div class="flex flex-wrap items-center gap-2 py-1">
            <div class="badge badge-outline text-[#b57dff] text-xs">Bootstrap</div>
            <div class="badge badge-outline text-[#f84600] text-xs">SCSS</div>
            <div class="badge badge-outline text-[#F8D900] text-xs">JavaScript</div>
          </div>
        </div>
        <div class="px-5 py-8 bg-[#282828] border border-[#484848] rounded-2xl flex flex-col justify-between"
          data-aos="zoom-in">
          <div>
            <i
              class="fa-solid fa-palette p-3 text-2xl sm:text-4xl bg-[#303030]  border border-[#606060] rounded-xl"></i>
            <a href="https://monky6503.github.io/colorGame-Vue-/" target="_blank"
              class="inline-block md:block ml-3 md:ml-0 mt-4 mb-2 text-white text-xl">Color Game</a>
            <p class="text-[#fff] text-sm sm:text-base py-3 md:py-4 indent-8">
              這是一個挑戰眼睛辨識力的遊戲，要點擊到不同顏色的方塊才會進到下一關，答錯則會扣分，越到後面的關卡會越難分辨。
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