<template>
    <div class="text-center">
        <img :src="element.img" :alt="element.name">
        <h2>{{ element.name }}</h2>
        <h2>{{ element.nickname }}</h2>
        <h3>{{ element.status }}</h3>
        <h3>{{ element.category }}</h3>
    </div>
</template>

<script>
export default {
    name: 'CardComponent',
    props: {
        element: Object
    }
}
</script>

<style lang="scss" scoped>

</style>