<template>
  <button @click="clickHandler">{{ buttonText }}</button>
</template>

<script>
export default {
  props: {
    buttonText: {
      type: String,
      required: false,
      default: "This is a button"
    }
  },
  emits: ["somebodyClickedTheButton"],
  methods: {
    clickHandler() {
      this.$emit("somebodyClickedTheButton");
    }
  }
};
</script>

<style scoped>
button {
  border: 2px solid black;
  border-radius: 5px;
  padding: 20px 35px;
  background-color: white;
  box-shadow: 5px 5px 5px rgb(0, 0, 0, 0.2);
  font-family:
    system-ui,
    -apple-system,
    BlinkMacSystemFont,
    "Segoe UI",
    Roboto,
    Oxygen,
    Ubuntu,
    Cantarell,
    "Open Sans",
    "Helvetica Neue",
    sans-serif;
  font-weight: bold;
  font-size: 20px;
}
</style>
