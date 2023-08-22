<template>
  <div>{{ counter }}</div>
  <TheButton @somebobyJustClickedMe="handleUp" buttonText="Up" />
  <TheButton @somebobyJustClickedMe="handleDown" buttonText="Down" />
</template>

<script>
import TheButton from "./components/TheButton.vue";
export default {
  components: { TheButton },
  data() {
    return {
      counter: 0
    };
  },
  methods: {
    handleUp() {
      this.counter++;
    },
    handleDown() {
      this.counter--;
    }
  }
};
</script>

<style scoped></style>
