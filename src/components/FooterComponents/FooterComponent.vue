<template>
    <footer>
        <div id="merchandising">
            <div class="container d-flex justify-content-around">
                <div class="row">
                    <MerchComponent class="col-2" v-for="(item, index) in merchandaisingItems" :key="index"
                        :item="item" />
                </div>

            </div>
        </div>
        <div id="menu">
            <div class="container d-flex flex-column flex-wrap align-content-start">
                <MenuComponent v-for="(menu, index) in menues" :key="index" :menu="menu" />
            </div>
        </div>
        <div id="contacts">
            <div class="container py-4 d-flex justify-content-between align-items-center ">
                <ButtonComponent />
                <div class="d-flex align-items-center justify-content-center gap-3">
                    <h4 class="mb-0 mx-3">Follow us</h4>
                    <ContactComponent v-for="(contact, index) in contacts" :key="index" :contact="contact" />
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
import { FooterMenu } from '../../data/database';
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
            merchandaisingItems: FooterMenu.merchandaisingItems,
            menues: FooterMenu.menues,
            contacts: FooterMenu.contacts
        }
    },
    methods: {

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