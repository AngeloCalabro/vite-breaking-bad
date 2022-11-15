<template>
    <div class="container p-4 cards-container">
        <NavbarComponent @filtercategory="getCharacters"/> 
        <div class="black-bar">
            <p>Found {{ store.characterList.length }} characters</p>
        </div>
        <CardComponent :characters="store.characterList" :loading="store.loading" />
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
            endPoint: 'characters',
        }
    },
    methods: {
        getCharacters() {
            store.errormessage = '';
            let options = null;
            if (store.search.category) {
                options = {
                    params: {
                        category: store.search.category,
                    }
                }
            };
            store.loading = true;
            const apiurl = store.apiURL + this.endPoint;
            axios.get(apiurl, options).then(
                (res) => {
                    store.characterList = [...res.data];
                    console.log(store.characterList);
                    store.loading = false;
                },
            ).catch((error)=>{
                store.characterList.length = 0;
                store.loading = false;
                store.errormessage = error.message
            })
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