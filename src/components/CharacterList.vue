<template>
    <div class="container">
        <div v-if="loading">
            Sto caricando...
        </div>
        <div class="row" v-if="!loading">
            <div class="col-12 col-sm-6 col-md-4 col-lg-3" v-for="(item, index) in characters" :key="item.char_id">
                <!-- <CardComponent :character="item" /> -->
                <div class="character">
                    <img :src="item.img" :alt="item.name">
                    <h2>{{ item.name }}</h2>
                    <h2>{{ item.nickname }}</h2>
                    <h3>{{ item.status }}</h3>
                </div>
                
            </div>
        </div>
    </div>
</template>

<script>
// import CardComponent from './components/CardComponent.vue';
export default {
    components: {
        // CardComponent
    },
    name: 'CharacterList',
    props: ['characters', 'loading']
}
</script>

<style lang="scss" scoped>

</style>