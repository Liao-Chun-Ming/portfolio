<script setup>
import { ref, onMounted } from 'vue'

const counter = ref(0)
const percent = ref(0)
const interValid = ref(null)
const isLoading = ref(true)

const startCounter = () => {
  interValid.value = setInterval(() => {
    percent.value = counter.value
    counter.value++
    if (counter.value === 101) {
      clearInterval(interValid.value)
    }
  }, 25)
}

onMounted(() => {
  startCounter()
  window.addEventListener('load', function () {
    setTimeout(function () {
      isLoading.value = false
    }, 2600)
  })
})
</script>
<template>
  <div class="preload" v-if="isLoading">
    <div class="counter">
      <p>Loading</p>
      <h1>{{ percent }}%</h1>
      <hr :style="{ width: percent + '%' }" />
    </div>
  </div>
</template>
<style scoped>
.preload {
  background: #0d0d0d;
  width: 100%;
  height: 100vh;
  position: fixed;
  z-index: 100;
  display: flex;
  justify-content: center;
  align-items: center;
}

.preload .counter {
  text-align: center;
}
.preload .counter p {
  font-size: 40px;
  font-weight: 400;
  color: #f60d54;
}
.preload .counter h1 {
  color: white;
  font-size: 55px;
  margin-top: -10px;
}
.preload .counter hr {
  background: #f60d54;
  border: none;
  height: 1px;
}

.preload .counter {
  position: relative;
  width: 200px;
}

/* .preload .counter h1.abs {
  position: absolute;
  top: 0%;
  width: 100%;
} */
/* .preload .counter .color {
  width: 0px;
  overflow: hidden;
  color: #f60d54;
} */
</style>
