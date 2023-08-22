<template>
  <input type="checkbox" @change="handleChange" />
</template>

<script>
export default {
  emits: ["change"],
  methods: {
    handleChange(event) {
      this.$emit("change", event.target.checked);
    }
  }
};
</script>

<style scoped></style>
