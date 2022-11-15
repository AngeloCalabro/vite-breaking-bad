<template>
    <div class="container">
        <div v-if="loading">
            Sto caricando...
        </div>
        <div class="row" v-if="!loading">
            <div class="col-12 col-sm-6 col-md-4 col-lg-3" v-for="(item, index) in character" :key="item.char_id">
                <CardComponent :element="item"/>
            </div>
        </div>
    </div>
</template>

<script>
import axios from 'axios';
import CardComponent from './CardComponent.vue';
export default {
    components: {
        CardComponent,
    },
    name: 'CharacterList',
    data(){
        return{
            apiURL: 'https://www.breakingbadapi.com/api/characters/',
            character: [],
            loading: false,
            
        }
    },
    methods: {
        getCharacters() {
            this.loading = true;
            axios.get(this.apiURL).then(
                (res) => {
                    this.characterList = [...res.data];
                    console.log(this.characterList)
                    this.loading = false;
                }
            ).catch((error) => {
                console.log(error);
            })
        }
    },
    created() {
        this.getCharacters()
    }
}
</script>

<style lang="scss" scoped>

</style>