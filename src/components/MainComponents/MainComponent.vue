<template>
    <main class="text-white d-flex flex-column align-items-center justify-content-center ">
        <JumbotronComponent :AbUrlImg="'/images/jumbotron.jpg'" />
        <div class="container">
            <MainButtonComponent id="current-series" :text="'CURRENT SERIES'" />
            <CardHighlightedComponent v-if="ComicsHighlighted" :style="{ height: HighLightDimension + 'px' }"
                :title="ComicsHighlighted.series" :img="ComicsHighlighted.thumb" :price="ComicsHighlighted.price"
                :disponibiliy="ComicsHighlighted.available" :series="ComicsHighlighted.type" />
            <div class="row gap-3 py-1 justify-content-center ">
                <CardComponent class="col-5 col-md-6 col-lg-3 col-xl-2 mb-4" v-for="(item, index) in ComicsCopy"
                    :key="index" :img="item.thumb" :title="item.series" @more-info="gestisci" />
            </div>
            <MainButtonComponent class="align-self-center" id="load-more" :text="'LOAD MORE'" />
        </div>
    </main>
</template>

<script>
import CardComponent from './CardComponent.vue';
import JumbotronComponent from './JumbotronComponent.vue';
import MainButtonComponent from './MainButtonComponent.vue';
import CardHighlightedComponent from './CardHighlightedComponent.vue';
import { Comics } from '../../data/database.js';
export default {
    name: 'MainComponent',
    data() {
        return {
            ComicsCopy: Comics,
            ComicsHighlighted: null,
            HighLightDimension: 450,
        }
    },
    components: {
        JumbotronComponent,
        CardComponent,
        MainButtonComponent,
        CardHighlightedComponent
    },
    mounted() {
        console.log(Comics);
    },
    methods: {
        gestisci(item) {
            const HighlightedElement = this.ComicsCopy.filter(element => {
                return (element.series === item.title && element.thumb === item.img)
            })
            this.ComicsHighlighted = HighlightedElement[0];
            let startingDimension = 0;
            // while (startingDimension <= this.HighLightDimension) {
            //     setTimeout(() => {
            //         startingDimension += 50
            //     }, 1000)
            // }


        }
    }
}
</script>

<style lang="scss" scoped>
@use '../../assets/styles/partials/variables' as *;

main {
    background-color: $contact-background;

    #current-series {
        transform: translateY(-50px);
        font-size: 2rem;
    }

    #load-more {
        margin: 20px auto 40px !important;
    }
}
</style>