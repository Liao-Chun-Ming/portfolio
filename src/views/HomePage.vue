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
  },
  methods: {
    handleScrollTo(section) {
      const mainView = this.$refs.mainView
      if (mainView && mainView.$refs[section]) {
        const element = mainView.$refs[section]
        window.scrollTo({
          top: element.$el.offsetTop - 20,
          behavior: 'smooth'
        })
      }
    }
  }
}
</script>
<template>
  <NavBar @scroll-to="handleScrollTo" />
  <HeaderView />
  <MainView ref="mainView" />
  <FooterView @scroll-to="handleScrollTo" />
</template>
