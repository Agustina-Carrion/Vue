<template>
  <div class="character-card">
    <img :src="character.image" alt="Character Image" />
    <div class="character-details">
      <h3>{{ character.name }}</h3>
      <span>Status: {{ character.status }}</span>
      <p>{{ character.species }}</p>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    character: Object
  }
};
</script>

<style scoped>
.character-card {
  width: 400px;
  height: 150px;
  display: flex;
  gap: 20px;
  border: solid 3px black;
  border-radius: 80px;
  box-shadow: 5px 5px 5px rgb(0, 0, 0, 0.5);
}
img {
  border-top-left-radius: 80px;
  border-bottom-left-radius: 80px;
  width: 50%;
  object-fit: cover;
}
.character-details {
  display: flex;
  flex-direction: column;
  gap: 10px;
}
h3 {
  margin: 1rem 0;
}
</style>
