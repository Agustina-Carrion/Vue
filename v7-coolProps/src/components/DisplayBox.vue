<template>
  <div class="display-box">
    <div v-if="displayText">{{ displayText }}</div>
    <div v-else>Please write something</div>
  </div>
</template>

<script>
export default {
  //   props: ["displayText"]
  props: {
    displayText: {
      //   type: String,
      // if more than one value type:
      type: [String, Number],
      required: true,
      default: "Default value"
    }
  }
};
</script>

<style scoped>
.display-box {
  background-color: var(--light-background-color);
  padding: var(--size-1);
  width: 300px;
  min-height: 300px;
  box-shadow: var(--shadow);
}
</style>
