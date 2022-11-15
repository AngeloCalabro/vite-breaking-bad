<template>
    <header class="p-2">
        <img class="img-fluid m-1" src="https://www.breakingbadapi.com/static/media/breaking_bad.6d275852.jpg" alt="breaking-bad logo">
        <h1 class="text-capitalize fw-bold m-1">Breaking Bad Api</h1>
    </header>
</template>

<script>
export default {
    name: 'AppHeader'
}
</script>

<style lang="scss" scoped>
header {
    display: flex;
        img {
        width: 50px
        }
}
</style>