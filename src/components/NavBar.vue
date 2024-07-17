<script>
</script>




<template>
  <nav class="w-full h-auto px-3 sm:px-7 md:px-14 py-4 flex justify-between items-center shadow-md rounded-b-lg"
    id="home">
    <div class="name text-xl sm:text-3xl">
      <p>From Data To Code</p>
    </div>
    <div class="hidden md:block">
      <ul class="flex text-xl gap-4">
        <li><a href="#home"
            class="no-underline decoration-slate-400 hover:text-slate-400  hover:underline underline-offset-4 transition-all ease-in duration-200">Home</a>
        </li>
        <li><a href="#about"
            class="no-underline decoration-slate-400 hover:text-slate-400  hover:underline underline-offset-4 transition-all ease-in duration-200">About</a>
        </li>
        <li><a href="#projects"
            class="no-underline decoration-slate-400 hover:text-slate-400  hover:underline underline-offset-4 transition-all ease-in duration-200">Projects</a>
        </li>
        <li><a href="#contact"
            class="no-underline decoration-slate-400 hover:text-slate-400  hover:underline underline-offset-4 transition-all ease-in duration-200">Contact</a>
        </li>
      </ul>
    </div>
    <div class="dropdown dropdown-end block md:hidden">
      <div tabindex="0" role="button">
        <i class="fa-solid fa-bars text-3xl"></i>
      </div>
      <ul tabindex="0" class="menu dropdown-content bg-base-100 rounded-box z-[1] mt-3 w-56 p-2 shadow text-xl">
        <li><a href="#home">Home</a></li>
        <li><a href="#about">About</a></li>
        <li><a href="#projects">Projects</a></li>
        <li><a href="#contact">Contact</a></li>
      </ul>
    </div>
  </nav>
</template>