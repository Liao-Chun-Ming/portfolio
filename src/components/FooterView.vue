<script>
export default {
  data() {
    return {
      year: ''
    }
  },
  mounted() {
    this.getYear()
  },
  methods: {
    getYear() {
      const now = new Date()
      this.year = now.getFullYear()
    }
  }
}
</script>

<template>
  <footer class="footer footer-center bg-base-200 text-base-content rounded p-10">
    <div class="flex flex-col sm:flex-row justify-between gap-4 text-xl">
      <a
        href="#home"
        class="no-underline decoration-slate-400 hover:text-slate-400 hover:underline underline-offset-4 transition-all ease-in duration-200"
        >Home</a
      >
      <a
        href="#about"
        class="no-underline decoration-slate-400 hover:text-slate-400 hover:underline underline-offset-4 transition-all ease-in duration-200"
        >About</a
      >
      <a
        href="#projects"
        class="no-underline decoration-slate-400 hover:text-slate-400 hover:underline underline-offset-4 transition-all ease-in duration-200"
        >Projects</a
      >
      <a
        href="#contact"
        class="no-underline decoration-slate-400 hover:text-slate-400 hover:underline underline-offset-4 transition-all ease-in duration-200"
        >Contact</a
      >
    </div>
    <aside>
      <p>Copyright © {{ year }}- All right reserved</p>
    </aside>
  </footer>
</template>
