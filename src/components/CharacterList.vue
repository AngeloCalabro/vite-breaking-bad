<template>
    <div class="container p-4 cards-container">
        <NavbarComponent @filtercategory="getCharacters"/> 
        <div class="black-bar">
            <p>Found {{ characterList.length }} characters</p>
        </div>
        <CardComponent :characters="characterList" :loading="loading" />
    </div>
</template>

<script>
import axios from 'axios';
import CardComponent from './CardComponent.vue';
import NavbarComponent from './NavbarComponent.vue';
import { store } from '../store';
export default {
    name: 'CharacterList',
    components: { CardComponent, NavbarComponent },
    data() {
        return {
            store,
            apiUrl: 'https://www.breakingbadapi.com/api/characters',
            characterList: [],
            loading: false,
        }
    },
    methods: {
        getCharacters() {
            this.loading = true;
            axios.get(this.apiUrl).then(
                (res) => {
                    this.characterList = [...res.data];
                    console.log(this.characterList);
                    this.loading = false;
                },
            )
            // .catch((error)=>{
            // console.log(error)
            // })
        }
    },
    created() {
        this.getCharacters()
    }
}
</script>

<style lang="scss" scoped>
@use '../assets/styles/partials/variables' as *;

.cards-container {
    background-color: white;
}

.black-bar {
    background-color: $black-bar;
    font-weight: bold;
    height: 50px;
    line-height: 50px;
    padding-left: 10px;
}
</style>