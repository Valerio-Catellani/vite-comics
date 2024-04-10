<template>
<footer>
    <div id="merchandising" >
    <div class="container d-flex justify-content-around">
        <div class="row">
            <MerchComponent class="col-2" v-for="(item, index) in merchandaisingItems" :key="index" :item="item"/>
            </div>
            
        </div>
    </div>
    <div id="menu">
        <div class="container d-flex flex-column flex-wrap align-content-start">
                <MenuComponent  v-for="(menu, index) in menues" :key="index" :menu="menu"/>
        </div>
    </div>
    <div id="contacts">
       <div class="container py-4 d-flex justify-content-between align-items-center ">
                <ButtonComponent /> 
                <div class="d-flex align-items-center justify-content-center gap-3">
                    <h4 class="mb-0">Follow us</h4>               
                    <ContactComponent v-for="(contact, index) in contacts" :key="index" :contact="contact"/>
                </div>
       </div>
    </div>
</footer>
</template>

<script>
import MerchComponent from './MerchComponent.vue';
import MenuComponent from './MenuComponent.vue';
import ButtonComponent from './ButtonComponent.vue';
import ContactComponent from './ContactComponent.vue';
    export default {
        name: 'FooterComponent',
        components: {
            MerchComponent,
            MenuComponent,
            ButtonComponent,
            ContactComponent,
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
                ],
                contacts: [
                    {
                        name:'facebook',
                        img: '/images/footer-facebook.png',
                        url: '#'
                    },
                    {
                        name:'Twitter',
                        img: '/images/footer-twitter.png',
                        url: '#'
                    },
                    {
                        name:'Youtube',
                        img: '/images/footer-youtube.png',
                        url: '#'
                    },
                    {
                        name:'Pinterest',
                        img: '/images/footer-pinterest.png',
                        url: '#'
                    },
                    {
                        name:'Periscope',
                        img: '/images/footer-periscope.png',
                        url: '#'
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

 #contacts {
    background-color: $contact-background;

    h4 {
        color: $navColor;
    }
 }

</style>