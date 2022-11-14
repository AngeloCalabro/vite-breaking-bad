<template>
    <div class="character text-center">
        <img :src="character.img" :alt="character.name">
        <h2>{{ character.name }}</h2>
        <h2>{{ character.nickname }}</h2>
        <h3>{{ character.status }}</h3>
        <h3>{{ character.category }}</h3>
    </div>
</template>

<script>
export default {
    name: 'CardComponent',
    props: {
        character: Object
    }
}
</script>

<style lang="scss" scoped>

</style>