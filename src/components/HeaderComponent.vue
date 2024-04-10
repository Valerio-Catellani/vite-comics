<template>
    <header >
        <div class="container d-flex justify-content-between h-100">
            <div id="img-container" class="h-100 p-2">
              <img class="img-fluid h-100" src="/images/dc-logo.png">  
            </div>
            <ul>
               <li v-for="(item, index) in navbar" :key="index"><a :href="item.url">{{ textUppercase(item.name)}}</a></li> 
            </ul>
        </div>
    </header>
</template>

<script>
export default {
        name: 'HeaderComponent',
        data() {
            return {
                navbar: [
                    {
                        name: 'Characters',
                        url: '#'
                    },
                    {
                        name: 'Comics',
                        url: '#'
                    },
                    {
                        name: 'Movies',
                        url: '#'
                    },
                    {
                        name: 'TV',
                        url: '#'
                    },
                    {
                        name: 'Games',
                        url: '#'
                    },
                    {
                        name: 'Collectibles',
                        url: '#'
                    },
                    {
                        name: 'Videos',
                        url: '#'
                    },
                    {
                        name: 'Fans',
                        url: '#'
                    },
                    {
                        name: 'News',
                        url: '#'
                    },
                    {
                        name: 'Shop',
                        url: '#'
                    }
                ]
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
@use '../assets/styles/partials/variables' as *;

header {
    height: 80px;
    background-color: $nav-background;
    flex-wrap: nowrap;

    #img-container {
        min-width: 100px;
    }

    ul {
        display: flex;
        list-style: none;
        margin-bottom: 0;
        height: 100%;
    
        li {
            margin: 0 1rem;
            display: flex;
            flex-direction: column;
            justify-content: center;
            height: 100%;
            padding: 0;
            position: relative;
    
            &::after {
                content: "";
                display: none;
                position: absolute;
                margin-left: 0 !important;
                bottom: 0;
                height: 7px;
                width: 100%;
                background-color: $navColor;
                margin-left: 1rem;
            }

            &:hover {
                &::after {
                    display: block;
                }
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
}

</style>