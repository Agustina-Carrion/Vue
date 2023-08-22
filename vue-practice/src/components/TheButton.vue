<template>
  <button @click="clickHandler">{{ buttonText }}</button>
</template>

<script>
export default {
  props: {
    buttonText: {
      type: String,
      required: true
    }
  },
  emits: ["clicked"],
  methods: {
    clickHandler() {
      this.$emit("clicked");
    }
  }
};
</script>

<style scoped></style>
