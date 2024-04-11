<template>
    <div v-if="splashPageAnimation != 0" class="splash-page position-fixed bg-dark start-0 top-0 w-100 h-100 d-flex"
        :style="{ opacity: splashPageAnimation + '%' }">

        <div class="img-container position-absolute" :style="{ opacity: logoAnimation.initial + '%' }">
            <img class="img-fluid" src="/images/splash-logo.png" alt="logo">
        </div>
        <div class="lux bg-light d-flex align-items-end" :style="{ height: lightAnimation.initial + 'vh' }">
            <div class="triangle"></div>
            <div class="bg-light"></div>
            <div class="triangle"></div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'SplashPageComponent',
    data() {
        return {
            lightAnimation: {
                initial: 0,
                final: 50,
            },
            logoAnimation: {
                initial: 0,
                final: 100,
            },
            splashPageAnimation: 100
        }
    },
    methods: {
        async lightAnimationGrow() {
            try {
                if (this.lightAnimation.initial < this.lightAnimation.final) {
                    while (this.lightAnimation.initial < this.lightAnimation.final) {
                        await new Promise(resolve => setTimeout(resolve, 5)); // 
                        this.lightAnimation.initial += 1;
                    }
                    this.logoAnimationAppear();

                }
            } catch (error) {
                console.log(error);
            }
        },
        async logoAnimationAppear() {
            try {
                if (this.logoAnimation.initial < this.logoAnimation.final) {
                    while (this.logoAnimation.initial < this.logoAnimation.final) {
                        await new Promise(resolve => setTimeout(resolve, 5)); // 
                        this.logoAnimation.initial += 1;
                    }
                    this.lightAnimation.initial = 0;
                    this.splashPageDisappear();
                }
            } catch (error) {
                console.log(error);
            }
        },
        async splashPageDisappear() {
            try {
                while (this.splashPageAnimation > 0) {
                    await new Promise(resolve => setTimeout(resolve, 8)); // 
                    this.splashPageAnimation -= 1;
                }
            } catch (error) {
                console.log(error);
            }
        },


    },
    mounted() {
        this.lightAnimationGrow();
    }
} 
</script>

<style lang="scss" scoped>
.splash-page {
    z-index: 100;
    // align-content: flex-end;
    align-items: flex-end;
    justify-content: center;

    .lux {
        width: 200px;
        // height: 50vh;
        opacity: 20%;
    }

    .triangle {
        width: 0;
        height: 0;
        border-left: 100px solid transparent;
        border-right: 100px solid transparent;
        border-bottom: 50vh solid #212529;
        transform: translateX(-50%);
    }

    .img-container {
        width: 50vh;
        height: 50vh;
        z-index: 200;
        bottom: calc(50vh - 25vh);


        img {
            filter: invert(100%);
        }

    }




}
</style>