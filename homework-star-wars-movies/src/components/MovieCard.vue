<template>
  <div class="movie-card">
    <div>Episode</div>
    <div class="episode-number">{{ movieObject.episode_id }}</div>
    <div>{{ movieObject.title }}</div>
    <button @click="clickHandler">Learn more</button>
  </div>
</template>

<script>
export default {
  props: {
    movieObject: {
      type: Object,
      required: true
    }
  },
  emits: ["movieSelect"],
  methods: {
    clickHandler() {
      this.$emit("movieSelect", this.movieObject);
    },
    intToRoman(num) {
      const romanNumerals = [
        { value: 1000, numeral: "M" },
        { value: 900, numeral: "CM" },
        { value: 500, numeral: "D" },
        { value: 400, numeral: "CD" },
        { value: 100, numeral: "C" },
        { value: 90, numeral: "XC" },
        { value: 50, numeral: "L" },
        { value: 40, numeral: "XL" },
        { value: 10, numeral: "X" },
        { value: 9, numeral: "IX" },
        { value: 5, numeral: "V" },
        { value: 4, numeral: "IV" },
        { value: 1, numeral: "I" }
      ];

      let result = "";

      for (const numeral of romanNumerals) {
        while (num >= numeral.value) {
          result += numeral.numeral;
          num -= numeral.value;
        }
      }

      return result;
    }
  }
};
</script>

<style scoped>
.movie-card {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 5px;
  width: 200px;
  min-height: 100px;
  background-color: lightgray;
  box-shadow: 5px 5px 5px rgba(28, 28, 28, 0.1);
  border-radius: 15px;
  padding: 10px;
}

button {
  background-color: lightgray;
  border: solid 3px black;
  font-weight: bold;
  cursor: pointer;
  padding: 4px;
  margin-top: 5px;
}
</style>
