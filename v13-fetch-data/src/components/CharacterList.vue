<template>
  <div v-if="isLoading">Loading...</div>
  <ul v-else class="character-list">
    <li v-for="character in characters">
      <CharacterCard :character="character" />
    </li>
  </ul>
</template>

<script>
import CharacterCard from "./CharacterCard.vue";
export default {
  components: { CharacterCard },
  data() {
    return {
      isLoading: true,
      characters: []
    };
  },
  async mounted() {
    const response = await fetch("https://swapi.dev/api/people");
    const result = await response.json();

    this.characters = result.results;

    this.isLoading = false;
  }
};
</script>

<style scoped>
.character-list {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
}
li {
  list-style: none;
}
</style>
