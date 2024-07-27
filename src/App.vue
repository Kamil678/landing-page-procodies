<script setup lang="ts">
import Header from "./components/Header.vue";
import MainSection from "./components/MainSection.vue";
import Footer from "./components/Footer.vue";
</script>

<template>
  <Header />
  <MainSection />
  <Footer />
</template>

<style lang="scss">
body {
  #app {
    max-width: 1200px;
    margin: 16px;
    color: #293632;

    @media (min-width: 992px) {
      margin: 16px auto;
      max-width: 900px;
    }

    @media (min-width: 1200px) {
      max-width: 1200px;
    }
  }
}
</style>
