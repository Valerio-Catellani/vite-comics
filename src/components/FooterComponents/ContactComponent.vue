<template>
    <div>
        <a :href="contact.url">
            <img :src="contact.img" :alt="contact.name" @click.prevent>
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

a:hover {
    opacity: 80%;
}
</style>