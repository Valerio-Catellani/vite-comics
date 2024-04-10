<template>
    <ul>
         <h3>{{ textUppercase(menu.name)}}</h3>
         <li v-for="(item, index) in menu.items" :key="index"><a :href="item.url">{{ item.name }}</a></li>
    </ul>
</template>

<script>
    export default {
        name: 'MenuComponent',
        props: ['menu'],
        methods: {
            textUppercase(text) {
                 return text.toUpperCase();
            }
        }
    }
</script>

<style lang="scss" scoped>
@use '../../assets/styles/partials/variables' as *;

ul {
    list-style: none;
    align-self: flex-start;
    h3 {
        color: $text-merch;
    }
    li {
        a{
            color: $text-menu;
            text-decoration: none;
            font-family: $font-menu;
            font-size: 0.8rem;
        }
    }
}

</style>