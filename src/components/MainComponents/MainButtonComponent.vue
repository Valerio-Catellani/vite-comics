<template>
    <div role="button" class="text-center py-2 m-4">{{ text }}</div>
</template>

<script>
export default {
    name: 'MainButtonComponent',
    props: ['text']
}
</script>

<style lang="scss" scoped>
@use '../../assets/styles/partials/variables' as *;

div {
    background-color: $navColor;
    width: 200px;

    &:hover {
        background-color: $button-hover;
    }
}
</style>