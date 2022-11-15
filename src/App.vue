<template>
  <AppHeader />
  <CharacterList />
</template>

<script>
import AppHeader from './components/AppHeader.vue';
import CharacterList from './components/CharacterList.vue';
export default {
  components: { AppHeader, CharacterList }
}
</script>

<style lang="scss" scoped>
@use './assets/styles/partials/variables' as *;
</style>