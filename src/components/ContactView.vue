<script setup>
import Swal from 'sweetalert2'
const copyEmail = (e) => {
  if (navigator.clipboard) {
    navigator.clipboard
      .writeText(e.target.innerText)
      .then(() => {
        Swal.fire({
          icon: 'success',
          title: 'Copied!!',
          text: e.target.innerText
        })
      })
      .catch((error) => {
        Swal.fire({
          icon: 'error',
          title: 'Oops...',
          text: error
        })
      })
  } else {
    Swal.fire({
      icon: 'question',
      title: 'Oops...',
      text: 'Your browser does not support this feature, please copy it manually.'
    })
  }
}
</script>

<template>
  <section id="contact">
    <h2 class="text-4xl font-semibold text-start pt-10 pb-5">Contact me</h2>
    <h3 class="text-2xl">Interested In ? You can contact me or follow me.</h3>
    <h3 class="text-2xl pb-8">Let's work together!!</h3>
    <div
      class="flex flex-col lg:flex-row flex-wrap items-start lg:items-center py-5 gap-5 lg:gap-10 text-lg sm:text-xl"
    >
      <div class="flex items-center justify-center">
        <i class="fa-solid fa-phone"></i>
        <p>：0923-383-635</p>
      </div>
      <div class="flex items-center justify-center">
        <i class="fa-solid fa-envelope"></i>
        <p id="email" class="cursor-pointer">
          ：<span @click="copyEmail">chunmingliao1018@gmail.com</span>
        </p>
      </div>
      <div class="flex items-center justify-center">
        <i class="fa-brands fa-github"></i>
        <p>：<a href="https://github.com/monky6503" target="_blank">My Github</a></p>
      </div>
      <div class="flex items-center justify-center">
        <i class="fa-brands fa-linkedin"></i>
        <p>：<a href="https://www.linkedin.com/in/chunming1018/" target="_blank">My LinkIn</a></p>
      </div>
      <div class="flex items-center justify-center">
        <i class="fa-solid fa-location-dot"></i>
        <p>：Beitun District,Taichung</p>
      </div>
    </div>
  </section>
</template>
