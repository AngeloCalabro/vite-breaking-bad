<template>
    <div class="p-5" v-if="loading">
        <p class="fw-bold text-black">Loading...</p>
    </div>
    <div class="d-flex flex-wrap" v-else="!loading">
        <div class="vz_col" v-for="(item) in characters" :key="item.char_id">
            <div class="single-card">
                <img :src="item.img" :alt="item.name" class="mb-2">
                <span class="fw-bold text-uppercase">{{ item.name }}</span>
                <div class="category-status">
                    <span>{{ item.category }}</span>
                    <br>
                    <span>{{ item.status }}</span>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'CardComponent',
    props: ['characters', 'loading']
}
</script>

<style lang="scss" scoped>
@use '../assets/styles/partials/variables' as *;

.vz_col {
    width: calc(100% / 5);

    .single-card {
        height: 400px;
        background-color: $bg-color;
        margin: 12px 15px;
        padding: 15px;
        text-align: center;

        .category-status {
            color: $text-gray;
            padding-top: 10px;

            span:last-of-type {
                font-size: 14px;
            }
        }
    }
}
</style>