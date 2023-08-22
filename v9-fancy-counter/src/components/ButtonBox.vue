<template>
  <div class="button-box">
    <TheButton @somebodyClickedTheButton="handleUp" buttonText="+1" />
    <TheButton @somebodyClickedTheButton="handleDown" buttonText="-1" />
    <TheButton @somebodyClickedTheButton="handleReset" buttonText="Reset" />
    <TheButton @somebodyClickedTheButton="handleUpTen" buttonText="+10" />
    <TheButton @somebodyClickedTheButton="handleDownTen" buttonText="-10" />
  </div>
</template>

<script>
import TheButton from "./TheButton.vue";
export default {
  components: {
    TheButton
  },
  emits: ["oneOfTheButtonsWasClicked"],
  methods: {
    handleUp() {
      this.$emit("oneOfTheButtonsWasClicked", 1);
    },
    handleDown() {
      this.$emit("oneOfTheButtonsWasClicked", -1);
    },
    handleReset() {
      this.$emit("oneOfTheButtonsWasClicked", 0);
    },
    handleUpTen() {
      this.$emit("oneOfTheButtonsWasClicked", 10);
    },
    handleDownTen() {
      this.$emit("oneOfTheButtonsWasClicked", -10);
    }
  }
};
</script>

<style scoped>
.button-box {
  display: flex;
  gap: 20px;
}
</style>
