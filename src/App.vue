<template>
  <Header />
  <HomeView />
  <!-- <RouterView /> -->
  <BackToTop />
  <Footer />
</template>

<script setup>
import { onMounted, ref } from "vue";
import { RouterLink, RouterView } from "vue-router";
import Header from "./components/Header.vue";
import Footer from "./components/Footer.vue";
import HomeView from "./views/HomeView.vue";
import BackToTop from "./components/BackToTop.vue";
</script>



<style lang="scss">
// @use "./assets/scss/main.scss";

#app {
  font-family: "Afacad Flux", sans-serif;
  font-weight: 400;
}
</style>
