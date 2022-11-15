<template>
  <div class=" container d-flex">
    <img class="img-fluid my-5" src="https://www.breakingbadapi.com/static/media/breaking_bad.6d275852.jpg" alt="Logo">
    <AppHeader title="Breaking Bad" />
  </div>
  <main>
    <!-- <AppSelection /> -->
    <CharacterList :characters="characterList" :loading="loading" />
  </main>
</template>

<script>
// import axios from 'axios';
import AppHeader from './components/AppHeader.vue';
// import AppSelection from './components/AppSelection.vue';
import CharacterList from './components/CharacterList.vue';
export default {
  components: {
    AppHeader,
    // AppSelection,
    CharacterList
  },
  // data() {
  //   return {
  //     apiURL: 'https://www.breakingbadapi.com/api/characters/',
  //     characterList: [],
  //     loading: false,
  //   }
  // },
  // methods: {
  //   getCharacters() {
  //     this.loading = true;
  //     axios.get(this.apiURL).then(
  //       (res) => {
  //         this.characterList = [...res.data];
  //         console.log(this.characterList)
  //         this.loading = false;
  //       }
  //     ).catch((error) => {
  //       console.log(error);
  //     })
  //   }
  // },
  // created() {
  //   this.getCharacters()
  // }

}
</script>

<style lang="scss" scoped>

img{
  width: 50px;
  height: 50px;
}

</style>