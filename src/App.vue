<template>
  <AppHeader />
  <CharacterList />
</template>

<script>
import AppHeader from './components/AppHeader.vue';
import CharacterList from './components/CharacterList.vue';
import { store } from './store';
export default {
  components: { AppHeader, CharacterList },
  data() {
    return {
      store
    }
  }
}
</script>

<style lang="scss" scoped>
@use './assets/styles/partials/variables' as *;
</style>