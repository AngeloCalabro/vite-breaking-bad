<template>
    <div class="character">
        <img :src="item.img" :alt="item.name">
        <h2>{{ item.name }}</h2>
        <h2>{{ item.nickname }}</h2>
        <h3>{{ item.status }}</h3>
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