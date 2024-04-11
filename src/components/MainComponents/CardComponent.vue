<template>
    <div class="card p-0" role="button" @click="$emit('more-info', this)">
        <div class="img-container">
            <img class="img-fluid" :src="img" :alt="title">
        </div>
        <h3 class="mb-0 mt-3">{{ title }}</h3>
    </div>
</template>

<script>
export default {
    name: 'CardComponent',
    props: ['img', 'title']
}
</script>

<style lang="scss" scoped>
@use '../../assets/styles/partials/variables' as *;

.card {
    min-width: 200px;
    max-width: 200px;
    background-color: transparent;
    border: none;
}


.img-container {
    aspect-ratio: 1 / 1;
    overflow: hidden;
}

h3 {
    background-color: transparent;
    color: $text-merch;
}
</style>