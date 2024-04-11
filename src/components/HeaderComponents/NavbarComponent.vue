<template>
    <div>
        <ul class="d-flex mb-0 h-100">
           <li v-for="(item, index) in menu" :key="index" @mouseover="hooverIndex=index" @mouseleave="hooverIndex=null">
                <a :href="item.url" @click="activeIndex=index" :class="{'color': index===activeIndex || index===hooverIndex}">{{item.name}}</a>
                <div v-if="index===activeIndex || index===hooverIndex" class="underline-bar"></div>
            </li> 
        </ul>
    </div>
</template>

<script>
    export default {
        name: 'NavbarComponent',
        props: ['menu'],
        data() {
            return {
                activeIndex : 0,
                hooverIndex : 0
            }
        },

    }

</script>

<style lang="scss" scoped>
@use '../../assets/styles/partials/variables' as *;



ul {

        list-style: none;

        @media screen and (max-width: 1200px) {
            display: none !important;   
         }

    
        li {
            margin: 0 1rem;
            display: flex;
            flex-direction: column;
            justify-content: center;
            height: 100%;
            padding: 0;
            position: relative;
    
            .underline-bar {
                display: block;
                position: absolute;
                margin-left: 0 !important;
                bottom: 0;
                height: 7px;
                width: 100%;
                background-color: $navColor;
                margin-left: 1rem;
            }

            &:hover {
                & a {
                    color: $navColor;
                }
                
            }
    
            a {
                margin: 0;
                text-decoration: none;
                color: black;
            }
        }
    }
    
    .color {
    color: $navColor;
}
</style>