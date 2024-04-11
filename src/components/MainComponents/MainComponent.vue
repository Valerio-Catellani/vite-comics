<template>
    <main class="text-white d-flex flex-column align-items-center justify-content-center ">
        <JumbotronComponent :AbUrlImg="'/images/jumbotron.jpg'" />
        <div class="container">
            <MainButtonComponent id="current-series" :text="'CURRENT SERIES'" />
            <CardHighlightedComponent ref="highlightedCard" v-if="ComicsHighlighted"
                :style="{ height: HighLightDimension.initial + 'px' }" :title="ComicsHighlighted.series"
                :img="ComicsHighlighted.thumb" :price="ComicsHighlighted.price"
                :disponibiliy="ComicsHighlighted.available" :series="ComicsHighlighted.type"
                @close-highlight="closeAnimation" />
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
            HighLightDimension: {
                initial: 0,
                final: 500
            }
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
            });
            if (this.ComicsHighlighted !== HighlightedElement[0]) {
                this.ComicsHighlighted = HighlightedElement[0];
                this.openAnimation();
                // Utilizza this.$nextTick() per eseguire il codice dopo che Vue ha completato le modifiche al DOM
                this.$nextTick(() => {
                    this.$refs.highlightedCard.$el.scrollIntoView({ behavior: 'smooth', block: 'start' });
                });
            } else {
                this.closeAnimation();
            }
        },
        async openAnimation() {
            try {
                if (this.HighLightDimension.initial < this.HighLightDimension.final) {
                    while (this.HighLightDimension.initial < this.HighLightDimension.final) {
                        await new Promise(resolve => setTimeout(resolve, 5)); // 
                        this.HighLightDimension.initial += 10;
                    }
                }
            } catch (error) {
                console.log(error);
            }
        },
        async closeAnimation() {
            try {
                if (this.HighLightDimension.initial >= this.HighLightDimension.final) {
                    while (this.HighLightDimension.initial > 0) {
                        await new Promise(resolve => setTimeout(resolve, 5));
                        this.HighLightDimension.initial -= 10;
                    }
                    this.ComicsHighlighted = null;
                }
            } catch (error) {
                console.log(error);
            }
        },

    },
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