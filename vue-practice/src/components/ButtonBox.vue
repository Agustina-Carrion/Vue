<template>
  <div class="button-box">
    <TheButton buttonText="Up" @clicked="handleClickUp" />
    <TheButton buttonText="Reset" @clicked="handleClickReset" />
    <TheButton buttonText="Down" @clicked="handleClickDown" />
  </div>
</template>

<script>
import TheButton from "./TheButton.vue";
export default {
  components: { TheButton },
  emits: ["buttonClicked"],
  methods: {
    handleClickUp() {
      this.$emit("buttonClicked", 1);
    },
    handleClickDown() {
      this.$emit("buttonClicked", -1);
    },
    handleClickReset() {
      this.$emit("buttonClicked", 0);
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
