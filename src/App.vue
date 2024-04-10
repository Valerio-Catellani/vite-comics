<template>
  <HeaderComponent />
  <MainComponent/>
  <FooterComponent />
</template>

<script>
import HeaderComponent from './components/HeaderComponents/HeaderComponent.vue';
import MainComponent from './components/MainComponent.vue';
import FooterComponent from './components/FooterComponents/FooterComponent.vue';
  export default {
    name: 'App',
    components: {
      HeaderComponent,
      MainComponent,
      FooterComponent
    }
  }
</script>

<style lang="scss" scoped>

</style>