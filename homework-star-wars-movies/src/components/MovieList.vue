<template>
  <div v-if="isLoading">Loading...</div>
  <div v-else>
    <h2>List of Star Wars movies:</h2>
    <div class="movie-list">
      <MovieCard
        v-for="movieObject in movieObjects"
        :key="movieObject.episode_id"
        :movieObject="movieObject"
        @movieSelect="movieSelectHandler"
      />
    </div>
  </div>
</template>

<script>
import MovieCard from "./MovieCard.vue";
export default {
  components: {
    MovieCard
  },
  data() {
    return {
      isLoading: true,
      movieObjects: []
    };
  },
  async created() {
    const response = await fetch("https://swapi.dev/api/films");
    const result = await response.json();
    this.movieObjects = result.results;
    this.isLoading = false;
  },
  emits: ["movieSelect"],
  methods: {
    movieSelectHandler(movieObject) {
      this.$emit("movieSelect", movieObject);
    }
  }
};
</script>

<style scoped>
.movie-list {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 30px;
}
</style>
