<template>
<footer>
    <div id="merchandising" >
    <div class="container d-flex justify-content-center">
            <MerchComponent v-for="(item, index) in merchandaisingItems" :key="index" :item="item"/>
        </div>
    </div>
    <div id="menu">
        <div class="container d-flex flex-column flex-wrap align-content-start">
            <MenuComponent v-for="(menu, index) in menues" :key="index" :menu="menu"/>
        </div>
    </div>
    <div>
        contacts
    </div>
</footer>
</template>

<script>
import MerchComponent from './MerchComponent.vue';
import MenuComponent from './MenuComponent.vue';
    export default {
        name: 'FooterComponent',
        components: {
            MerchComponent,
            MenuComponent
        },
        data() {
            return {
                merchandaisingItems: [
                    {
                        name: 'Digital Comics',
                        img: '/images/buy-comics-digital-comics.png'
                    },
                    {
                        name: 'DC Merchandise',
                        img: '/images/buy-comics-merchandise.png'
                    },
                    {
                        name: 'Subscription',
                        img: '/images/buy-comics-subscriptions.png'
                    },
                    {
                        name: 'Comic Shop Locator',
                        img: '/images/buy-comics-shop-locator.png'
                    },
                    {
                        name: 'DC Power Visa',
                        img: '/images/buy-dc-power-visa.svg'
                    }
                ],
                menues: [
                    {
                        name: 'Dc Comics',
                        items : [
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
                                name: 'Videos',
                                url: '#'
                            },
                            {
                                name: 'News',
                                url: '#'
                            }

                        ]
                    },
                    {
                        name: 'Shop',
                        items : [
                            {
                                name: 'Shop DC',
                                url: '#'
                            },
                            {
                                name: 'Shop DC Collectibles',
                                url: '#'
                            }
                        ]
                    },
                    {
                        name: 'DC',
                        items : [
                            {
                                name: 'Terms Of Use',
                                url: '#'
                            },
                            {
                                name: 'Privacy policy (New)',
                                url: '#'
                            },
                            {
                                name: 'Ad Choices',
                                url: '#'
                            },
                            {
                                name: 'Advertising',
                                url: '#'
                            },
                            {
                                name: 'Jobs',
                                url: '#'
                            },
                            {
                                name: 'Subscriptions',
                                url: '#'
                            },
                            {
                                name: 'Talent Workshops',
                                url: '#'
                            },
                            {
                                name: 'CPSC Certificates',
                                url: '#'
                            },
                            {
                                name: 'Ratings',
                                url: '#'
                            },
                            {
                                name: 'Shop Help',
                                url: '#'
                            },
                            {
                                name: 'Contact Us',
                                url: '#'
                            }
                        ]
                    },
                    {
                        name: 'Sites',
                        items : [
                            {
                                name: 'DC',
                                url: '#'
                            },
                            {
                                name: 'MAD Magazine',
                                url: '#'
                            },
                            {
                                name: 'DC Kids',
                                url: '#'
                            },
                            {
                                name: 'DC Universe',
                                url: '#'
                            },
                            {
                                name: 'DC Power Visa',
                                url: '#'
                            }
                        ]
                    }
                ]
            }
        }
    }
</script>

<style lang="scss" scoped>
@use '../../assets/styles/partials/variables' as *;

 #merchandising {
    background-color: $merchant-background;
 }


 #menu {
    background-image: url('/images/footer-bg.jpg');
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;

    .container {
        background-image: url('/images/dc-logo-bg.png');
        background-position: right;
        background-repeat: no-repeat;
        height: 500px;
        padding: 30px 0;
    }
 }

</style>