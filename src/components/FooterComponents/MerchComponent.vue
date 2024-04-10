<template>
    <div class="merch-container d-flex align-items-center justify-content-center py-5 px-2">
        <div class="img-container d-flex align-items-center justify-content-center">
            <img class="img-fluid h-100" :src="item.img" :alt="item.name">
        </div>
        <h5>{{ textUppercase(item.name) }}</h5>
    </div>
</template>

<script>
    export default {
        name: 'MerchComponent',
        props: ['item'],
        methods: {
            textUppercase(text) {
                 return text.toUpperCase();
            }
        }
    }
</script>

<style lang="scss" scoped>
@use '../../assets/styles/partials/variables' as *;

.merch-container {
    color: $text-merch;
    min-width: 200px;

    .img-container{
        width: 60px;
        height: 60px;
        min-width: 60px;
        min-height: 60px;
    }

    h5 {
        font-size: 1rem;
        padding-left: 10px;
        margin-bottom: 0;
        cursor: pointer;
    }
}

</style>