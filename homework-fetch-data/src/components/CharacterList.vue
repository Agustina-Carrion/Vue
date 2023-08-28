<template>
  <div v-if="isLoading">Loading...</div>
  <div v-else>
    <h1>RICK & MORTY CHARACTERS</h1>
    <ul class="character-list">
      <li v-for="(character, i) in characters" :key="i">
        <CharacterCard :character="character" />
      </li>
    </ul>
  </div>
</template>

<script>
import CharacterCard from "./CharacterCard.vue";
export default {
  components: {
    CharacterCard
  },
  data() {
    return {
      isLoading: true,
      characters: []
    };
  },
  async mounted() {
    const response = await fetch("https://rickandmortyapi.com/api/character");
    const result = await response.json();
    console.log(result.results);
    this.characters = result.results;
    this.isLoading = false;
  }
};
</script>

<style scoped>
h1 {
  text-align: center;
  margin: 50px;
}
.character-list {
  display: flex;
  flex-wrap: wrap;
  gap: 30px;
  justify-content: center;
  padding: 0;
}
li {
  list-style: none;
}
</style>
