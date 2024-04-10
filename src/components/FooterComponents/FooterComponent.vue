<template>
<footer>
    <div id="merchandising" >
    <div class="container d-flex justify-content-center ">
            <MerchComponent v-for="(item, index) in merchandaisingItems" :key="index" :item="item"/>
        </div>
    </div>
    <div>
        menu
    </div>
    <div>
        contacts
    </div>
</footer>
</template>

<script>
import MerchComponent from './MerchComponent.vue'
    export default {
        name: 'FooterComponent',
        components: {
            MerchComponent
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

</style>