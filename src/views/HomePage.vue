<script>
import NavBar from '../components/NavBar.vue'
import HeaderView from '../components/HeaderView.vue'
import MainView from '../components/MainView.vue'
import FooterView from '../components/FooterView.vue'
export default {
  components: {
    NavBar,
    HeaderView,
    MainView,
    FooterView
  }
}
</script>
<template>
  <NavBar />
  <HeaderView />
  <MainView />
  <FooterView />
</template>
