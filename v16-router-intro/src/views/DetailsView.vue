<template>
  <div class="detail-view">
    <RouterLink to="/" class="back-button">Back</RouterLink>
    <div v-if="isLoading" class="loading-spinner"></div>
    <div v-else class="detail-section">
      <img :src="pokemonName.sprites?.other['official-artwork'].front_default" />
      <!-- <h3>Name: {{ $route.query.name }}</h3> -->
      <div class="pokemon-details">
        <h1>{{ formatPokemonName }}</h1>
        <p><span>Height:</span> {{ pokemonName.height }}</p>
        <p><span>Base Experience: </span> {{ pokemonName.base_experience }}</p>
        <p>
          <span>Description: </span>Lorem ipsum dolor sit amet consectetur adipisicing elit. Modi,
          suscipit nisi! Dicta necessitatibus fugiat, cum voluptate quaerat rerum dolore quasi
          expedita eum? Sit beatae deserunt porro voluptas eum at. Sapiente, aut omnis. Culpa eaque
          voluptatum tenetur similique deserunt? Incidunt ipsum quisquam id. Quod laudantium a
          consequatur distinctio molestias hic nam ratione animi? Eaque, architecto repudiandae?
          Possimus aspernatur, saepe numquam perspiciatis nam placeat distinctio quidem beatae
          ratione esse minus laboriosam illo nostrum iste aliquam asperiores tenetur ipsum eaque
          animi quas vel? Quia consequuntur accusamus est qui, voluptates at laudantium, maxime
          culpa tempora molestias officia incidunt. Vero modi quo dolores illum animi?
        </p>
      </div>
    </div>
  </div>
</template>

<script>
function capitalizeFirstLetter(string) {
  return string.charAt(0).toUpperCase() + string.slice(1);
}

export default {
  data() {
    return {
      pokemonName: {},
      isLoading: true
    };
  },
  computed: {
    formatPokemonName() {
      return this.pokemonName.name ? capitalizeFirstLetter(this.pokemonName.name) : "";
    }
  },
  async mounted() {
    // this.pokemonName = this.$route.query.name;

    const response = await fetch(`https://pokeapi.co/api/v2/pokemon/${this.$route.query.name}`);
    const result = await response.json();

    this.pokemonName = result;
    this.isLoading = false;
  }
};
</script>

<style scoped>
.back-button {
  background-color: white;
  width: 100px;
  height: 30px;
  display: flex;
  justify-content: center;
  align-items: center;
  border: solid 2px black;
  text-transform: uppercase;
  text-decoration: none;
  color: black;
}
.detail-view {
  display: flex;
  flex-direction: column;
  gap: 10px;
}
.loading-spinner {
  margin: 0 auto;
  width: 100px;
  height: 100px;
  border: 10px solid #ccc;
  border-bottom-color: #ff3d00;
  border-radius: 50%;
  display: inline-block;
  box-sizing: border-box;
  animation: rotation 1s linear infinite;
}
@keyframes rotation {
  0% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
  }
}
.detail-section {
  width: 100vw;
  height: 80vh;
  display: flex;
  gap: 20px;
  justify-content: start;
}
img {
  border-top-left-radius: 80px;
  border-top-right-radius: 80px;
  width: 50%;
  object-fit: contain;
}
.pokemon-details {
  width: 50%;
  display: flex;
  flex-direction: column;
  gap: 5px;
  padding: 50px;
}
h3 {
  margin: 1rem 0;
}
span {
  font-style: italic;
}
</style>
