<template>
    <div class="container">
        <div v-if="loading">
            Sto caricando...
        </div>
        <div class="row" v-if="!loading">
            <div class="col-12 col-sm-6 col-md-4 col-lg-3" v-for="(item, index) in character" :key="item.char_id">
                <CardComponent :character="item" />
            </div>
        </div>
    </div>
</template>

<script>
import CardComponent from './CardComponent.vue';
export default {
    components: {
        CardComponent,
    },
    name: 'CharacterList',
    props: ['character', 'loading']
}
</script>

<style lang="scss" scoped>

</style>