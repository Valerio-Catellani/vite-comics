<template>
    <header>
        <div class="container d-flex justify-content-between h-100">
            <div id="img-container" class="h-100 p-2">
                <img class="img-fluid h-100" src="/images/dc-logo.png">
            </div>
            <NavbarComponent :menu="navbar" />
            <KebabMenu :menu="navbar" :dimensionOriginalBar="80" />
        </div>
    </header>
</template>

<script>
import KebabMenu from './KebabMenu.vue';
import NavbarComponent from './NavbarComponent.vue';
import { HeaderMenu } from '../../data/database.js';
export default {
    name: 'HeaderComponent',
    components: {
        KebabMenu,
        NavbarComponent,
    },
    data() {
        return {
            navbar: HeaderMenu
        }
    },
    methods: {
        textUppercase(text) {
            return text.toUpperCase();
        }
    }
}
</script>

<style lang="scss" scoped>
@use '../../assets/styles/partials/variables' as *;

header {
    height: 80px;
    background-color: $nav-background;
    flex-wrap: nowrap;


    #img-container {
        min-width: 100px;
    }

}
</style>