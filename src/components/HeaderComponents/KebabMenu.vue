<template>
        <div id="kebab-menu-container" class="align-content-center px-5 position-relative">
                <i class="fa-solid fa-bars fs-1" role="button" tabindex="0" @click="isOpen = !isOpen" @blur="isOpen = false"></i>
                <div v-if="isOpen" class="ul-container position-absolute ">
                    <ul>
                        <li v-for="(item, index) in menu" :key="index"><a :href="item.url">{{ item.name }}</a></li>
                    </ul>
                </div>
        </div>
</template>

<script>
    export default {
        name: 'KebabMenu',
        props: ['menu'],
        data() {
            return {
                isOpen: false
            }
        }
    }
</script>

<style lang="scss" scoped>
@use '../../assets/styles/partials/variables' as *;


#kebab-menu-container {
        display: none;
        @media screen and (max-width: 1200px) {
            display: block;
        }

    .ul-container{
        background-color: $nav-background;
        top:80px;
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
}
</style>