<template>
    <div class="search-bar ps-2 my-3">
        <select name="category" @change="searchCategory" v-model="store.category" class="mx-1">
            <option selected value="">Select category</option>
            <option :value="cat" v-for="(cat, index) in category" :key="index">{{ cat }}</option>
        </select>
        <select name="status" @change="searchCategory" v-model="store.status" class="mx-1">
            <option selected value="">Select status</option>
            <option :value="stat" v-for="(stat, index) in status" :key="index">{{ stat }}</option>
        </select>
    </div>
</template>

<script>
import { store } from '../store';
export default {
    name: 'NavbarComponent',
    data(){
        return{
            store,
            category :[
                'Breaking Bad',
                'Better Call Saul'
            ],
            status: [
                'Presumed dead',
                'Deceased',
                'Alive',
                'Unknown'
            ]
        }
    },
    methods: {
        searchCategory() {
            this.$emit('filtercategory');
        }
    }
}
</script>

<style lang="scss" scoped>
.search-bar select {
    padding: 5px;
    font-size: 13px;
    border-radius: 5px;
}
</style>