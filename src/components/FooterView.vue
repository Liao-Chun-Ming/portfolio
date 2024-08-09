<script setup>
import { ref, onMounted, defineEmits } from 'vue'
const year = ref('')

const getYear = () => {
  const now = new Date()
  year.value = now.getFullYear()
}
const emit = defineEmits(['scroll-to'])

const scrollTo = (elementId) => {
  emit('scroll-to', elementId)
}
onMounted(() => {
  getYear()
})
</script>

<template>
  <footer class="footer footer-center bg-base-200 text-base-content rounded p-10">
    <div class="flex flex-col sm:flex-row justify-between gap-4 text-xl">
      <button
        @click="scrollTo('about')"
        class="no-underline decoration-[#577B8D] hover:text-[#577B8D] hover:underline underline-offset-4 transition-all ease-in duration-200"
      >
        About
      </button>
      <button
        @click="scrollTo('projects')"
        class="no-underline decoration-[#577B8D] hover:text-[#577B8D] hover:underline underline-offset-4 transition-all ease-in duration-200"
      >
        Projects
      </button>
      <button
        @click="scrollTo('contact')"
        class="no-underline decoration-[#577B8D] hover:text-[#577B8D] hover:underline underline-offset-4 transition-all ease-in duration-200"
      >
        Contact
      </button>
    </div>
    <aside>
      <p>Copyright © {{ year }}- All right reserved</p>
    </aside>
  </footer>
</template>
