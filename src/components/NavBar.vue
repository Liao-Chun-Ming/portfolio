<script>
export default {
  name: 'App',
  methods: {
    scrollTo(elementId) {
      this.$emit('scroll-to', elementId)
    }
  }
}
</script>

<template>
  <nav
    class="w-11/12 h-auto px-3 sm:px-7 md:px-10 py-4 mx-auto flex justify-between items-center"
    ref="home"
  >
    <div class="name text-xl sm:text-3xl">
      <p>From Data To Code</p>
    </div>
    <div class="hidden md:block">
      <ul class="flex text-xl gap-4">
        <li>
          <button
            @click="scrollTo('about')"
            class="no-underline decoration-[#577B8D] hover:text-[#577B8D] hover:underline underline-offset-4 transition-all ease-in duration-200"
          >
            About
          </button>
        </li>
        <li>
          <button
            @click="scrollTo('projects')"
            class="no-underline decoration-[#577B8D] hover:text-[#577B8D] hover:underline underline-offset-4 transition-all ease-in duration-200"
          >
            Projects
          </button>
        </li>
        <li>
          <button
            @click="scrollTo('contact')"
            class="no-underline decoration-[#577B8D] hover:text-[#577B8D] hover:underline underline-offset-4 transition-all ease-in duration-200"
          >
            Contact
          </button>
        </li>
      </ul>
    </div>
    <div class="dropdown dropdown-end block md:hidden">
      <div tabindex="0" role="button">
        <i class="fa-solid fa-bars text-3xl"></i>
      </div>
      <ul
        tabindex="0"
        class="menu dropdown-content bg-base-100 rounded-box z-[1] mt-3 w-56 p-2 top-10 shadow text-xl"
      >
        <li><button @click="scrollTo('about')">About</button></li>
        <li><button @click="scrollTo('projects')">Projects</button></li>
        <li><button @click="scrollTo('contact')">Contact</button></li>
      </ul>
    </div>
  </nav>
</template>
