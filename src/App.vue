<script>
import MainHeader from './components/MainHeader.vue';
import MainPage from './components/MainPage.vue';
import BlueBan from './components/BlueBan.vue';
import FooterBan from './components/FooterBan.vue';
import MainFooter from './components/MainFooter.vue';


export default {
  components: {
    MainHeader,
    MainPage,
    BlueBan,
    FooterBan,
    MainFooter
  }
}

</script>

<template>
  <MainHeader />
  <MainPage />
  <BlueBan />
  <FooterBan />
  <MainFooter />
</template>

<style lang="scss">
@use "./styles/general.scss" as *;
</style>
