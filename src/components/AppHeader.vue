<template>
    <header class="p-2">
        <img src="https://www.breakingbadapi.com/static/media/breaking_bad.6d275852.jpg" alt="breaking-bad logo">
        <span class="text-capitalize fw-bold">Breaking Bad Api</span>
    </header>
</template>

<script>
export default {
    name: 'AppHeader'
}
</script>

<style lang="scss" scoped>
header img {
    width: 50px
}

header span {
    font-size: 25px;
    vertical-align: middle;
}
</style>