<template>
  <div>
    <TheStarWarsMovieList />
    <CharacterList />
  </div>
</template>

<script>
import TheStarWarsMovieList from "./components/TheStarWarsMovieList.vue";
import CharacterList from "./components/CharacterList.vue";
export default {
  components: { TheStarWarsMovieList, CharacterList }
};
</script>

<style scoped></style>
