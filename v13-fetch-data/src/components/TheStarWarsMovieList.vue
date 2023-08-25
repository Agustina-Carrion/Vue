<template>
  <!-- <div v-if="movies.length === 0">Loading ...</div> -->
  <div v-if="isLoading">Loading...</div>
  <div v-else>
    <ul>
      <li v-for="movie in movies">
        {{ movie.title }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isLoading: true,
      movies: []
    };
  },
  async mounted() {
    const response = await fetch("https://swapi.dev/api/films");
    const result = await response.json();

    this.movies = result.results;
    this.isLoading = false;
  }
};
</script>

<style scoped></style>
