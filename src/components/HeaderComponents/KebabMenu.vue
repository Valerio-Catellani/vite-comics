<template>
  <div id="kebab-menu-container" class="align-content-center px-5 position-relative">
    <i class="fa-solid fa-bars fs-1" role="button" tabindex="0" @click="toggleMenu" @blur="isOpen = false"></i>
    <div v-if="isOpen" class="ul-container position-absolute transition-open-menu"
      :style="{ top: dimensionOriginalBar + 'px' }">
      <ul>
        <li v-for="(item, index) in menu" :key="index"><a :href="item.url">{{ item.name }}</a></li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: 'KebabMenu',
  props: ['menu', 'dimensionOriginalBar'],
  data() {
    return {
      isOpen: false,
    }
  },
  methods: {
    toggleMenu() {
      this.isOpen = !this.isOpen;
    }
  }
}
</script>

<style lang="scss" scoped>
@use '../../assets/styles/partials/variables' as *;

#kebab-menu-container {
  display: none;
  z-index: 400;

  @media screen and (max-width: 1200px) {
    display: block;
  }

  .ul-container {
    background-color: $nav-background;
    left: 0;

    ul {
      list-style: none;
      padding: 20px;

      li {
        padding: 5px 0;

        a {
          text-decoration: none;
          color: $navInactive;

          &:hover {
            color: $navColor;
          }
        }
      }
    }
  }

  // Definizione della transizione
  .transition-open-menu {
    transition: height 1s ease; // Durata della transizione di 0.3 secondi
    height: auto; // Inizialmente l'altezza è auto per far espandere il menu gradualmente
  }
}
</style>