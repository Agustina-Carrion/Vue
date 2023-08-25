<template>
  <button @click="handleReset">Reset</button>
</template>

<script>
export default {
  emits: ["resetPassword"],
  methods: {
    handleReset() {
      this.$emit("resetPassword");
    },
  },
};
</script>

<style scoped></style>
