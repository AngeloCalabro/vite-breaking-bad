<template>
    <div>
        <header class="container">
            <h1 class="text-center m-5">{{ title }}</h1>
        </header>
    </div>
</template>

<script>
export default {
    name: 'AppHeader',
    props: {
        title: String
    }
}
</script>

<style lang="scss" scoped>
h1 {
    font-weight: 700;
}
</style>