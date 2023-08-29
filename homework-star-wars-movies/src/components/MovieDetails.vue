<template>
  <div v-if="movieObject == undefined">Select a movie on the left</div>
  <div v-else>
    <h2>Episode {{ movieObject.episode_id }} - {{ movieObject.title }}</h2>
    <p>{{ movieObject.opening_crawl }}</p>
    <div>{{ numberLoaded }} / {{ totalCharacters }}</div>
    <div>{{ Math.round((numberLoaded / totalCharacters) * 100) }} %</div>
    <ul>
      <li v-for="character in characterNames" :key="character">
        {{ character }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: {
    movieObject: {
      type: Object,
      required: false
    }
  },
  data() {
    return {
      characterNames: [],
      numberLoaded: 0,
      totalCharacters: 0
    };
  },
  watch: {
    async movieObject() {
      // This line cleans the list when there's any change to the movieObject
      this.characterNames = [];
      this.totalCharacters = this.movieObject.characters.length;

      for (let i = 0; i < this.movieObject.characters.length; i++) {
        const characterURL = this.movieObject.characters[i];

        const response = await fetch(characterURL);
        const result = await response.json();

        this.numberLoaded = i + 1;

        this.characterNames.push(result.name);
      }
    }
  }
};
</script>

<style scoped></style>
