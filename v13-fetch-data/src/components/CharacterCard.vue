<template>
  <div class="character">
    <h4>{{ character.name }}</h4>
    <p>Height: {{ giveHeightFormat }}</p>
    <p>Birth Year: {{ character.birth_year }}</p>
  </div>
</template>

<script>
export default {
  props: {
    character: Object
  },
  computed: {
    giveHeightFormat() {
      return this.character.height / 100 + " cm";
    }
  }
};
</script>

<style scoped>
.character {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 5px;
  border: solid 3px black;
  border-radius: 10px;
  width: 250px;
  height: 150px;
  padding: 10px;
}

h4 {
  margin: 0;
}
</style>
