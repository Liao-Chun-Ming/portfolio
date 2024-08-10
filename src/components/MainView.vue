<script>
import AboutView from '../components/AboutView.vue'
import ProjectView from '../components/ProjectView.vue'
import ContactView from '../components/ContactView.vue'
import lottie from 'lottie-web'
export default {
  data() {
    return {
      isVisible: false
    }
  },
  components: {
    AboutView,
    ProjectView,
    ContactView
  },
  mounted() {
    this.loadAnimation(), window.addEventListener('scroll', this.scrollFunction)
  },
  beforeUnmount() {
    window.removeEventListener('scroll', this.scrollFunction)
  },
  methods: {
    scrollFunction() {
      this.isVisible = window.scrollY > 500 ? true : false
    },
    goTop() {
      window.scrollTo({
        top: 0,
        behavior: 'smooth'
      })
    },
    loadAnimation() {
      lottie.loadAnimation({
        container: this.$refs.goTop,
        renderer: 'svg',
        loop: true,
        autoplay: true,
        path: 'arrowUp.json'
      })
    }
  }
}
</script>
<template>
  <main class="text-xl bg-[#f5f5f5]">
    <div class="w-5/6 m-auto py-8">
      <AboutView ref="about" />
      <ProjectView ref="projects" />
      <ContactView ref="contact" />
    </div>
    <button
      type="button"
      ref="goTop"
      @click="goTop"
      v-show="isVisible"
      class="w-14 h-14 bg-black rounded-full sticky left-[95%] bottom-0 translate-x-[-10%] translate-y-[-50%]"
    ></button>
  </main>
</template>
