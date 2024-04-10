<template>
    <button role="button">
        SING-UP NOW!
    </button>
</template>

<script>
    export default {
        name: 'ButtonComponent',
    }
</script>

<style lang="scss" scoped>

@use '../../assets/styles/partials/variables' as *;

 button {
    border: $navColor 2px solid;
    background-color: transparent;
    font-size: 2rem;
    color: $text-merch;
    padding: 10px 20px;

    &:hover{
        background-color: $navColor;
    }
 }
</style>