<template>
    <div class="jumbotron-container">
        <img class="vw-100 img-fluid" :src="AbUrlImg" alt="Jumbotron">
    </div>
</template>

<script>
export default {
    name: 'JumbotronComponent',
    props: ['AbUrlImg']
}
</script>

<style lang="scss" scoped>
.jumbotron-container {
    height: 400px;
    overflow: hidden;

    @media screen and (max-width: 768px) {
        height: 200px;
    }
}
</style>