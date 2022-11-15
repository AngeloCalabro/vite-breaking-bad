<template>
    <div class="p-5" v-if="store.loading">
        <p class="fw-bold text-black text-center">Loading...</p>
    </div>
    <div class="d-flex flex-wrap" v-else="!store.loading">
        <div class="my_col" v-for="(item) in characters" :key="item.char_id">
            <div class="card single-card">
                <img :src="item.img" :alt="item.name" class="img-fluid mb-2">
                <h6 class="fw-bold text-uppercase">{{ item.name }}</h6>
                <div class="category-status">
                    <h6>{{ item.category }}</h6>
                    <h6>{{ item.status }}</h6>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import { store } from '../store';
export default {
    name: 'CardComponent',
    props: ['characters'],
    data(){
        return{
            store
        }
    }
}
</script>

<style lang="scss" scoped>
@use '../assets/styles/partials/variables' as *;

.my_col {
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
        }
    }
}
</style>