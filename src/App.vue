<template>
  <SplashPageComponent />
  <HeaderComponent />
  <MainComponent />
  <FooterComponent />
</template>

<script>
import HeaderComponent from './components/HeaderComponents/HeaderComponent.vue';
import MainComponent from './components/MainComponents/MainComponent.vue';
import FooterComponent from './components/FooterComponents/FooterComponent.vue';
import SplashPageComponent from './components/SplashPageComponent.vue';
export default {
  name: 'App',
  components: {

    HeaderComponent,
    MainComponent,
    FooterComponent,
    SplashPageComponent
  }
}
</script>

<style lang="scss" scoped></style>