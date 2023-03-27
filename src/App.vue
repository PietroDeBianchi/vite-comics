<script setup>
import MainHeader from './components/MainHeader.vue'
import MainPage from './components/MainPage.vue'
import BlueBan from './components/BlueBan.vue'
import FooterBan from './components/FooterBan.vue'
import MainFooter from './components/MainFooter.vue'
</script>

<template>
  <MainHeader />
  <MainPage />
  <BlueBan />
  <FooterBan />
  <MainFooter />
</template>

<style lang="scss">
@use "./styles/general.scss";
</style>
