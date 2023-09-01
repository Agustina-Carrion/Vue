<template>
  <h1>Pokemon List</h1>
  <ul class="pokemon-list">
    <li v-for="name in pokemonNames" :key="name">
      <RouterLink :to="`/details?name=${name}`"> ❇️ {{ name }} </RouterLink>
    </li>
  </ul>
</template>

<script>
export default {
  data() {
    return {
      pokemonNames: []
    };
  },
  async created() {
    const response = await fetch("https://pokeapi.co/api/v2/pokemon?limit=50");
    const result = await response.json();

    for (let i = 0; i < result.results.length; i++) {
      const pokemonNames = result.results[i].name;
      this.pokemonNames.push(pokemonNames);
    }
  }
};
</script>

<style scoped>
.pokemon-list {
  list-style-type: none;
  padding: 0 20px;
  font-size: large;
}

.pokemon-list li {
  margin-bottom: 10px;
}

.pokemon-list li a {
  text-decoration: none;
  color: black;
}

.pokemon-list li a:hover {
  font-weight: bold;
}
</style>
