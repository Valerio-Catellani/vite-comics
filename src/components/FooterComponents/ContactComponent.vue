<template>
    <div>
        <a :href="contact.url">
            <img :src="contact.img" :alt="contact.name">
        </a>
    </div>
</template>

<script>
    export default {
        name: 'ContactComponent',
        props: ['contact'],
    }
</script>

<style lang="scss" scoped>
@use '../../assets/styles/partials/variables' as *;

</style>