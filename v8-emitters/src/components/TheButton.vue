<template>
  <div>
    <button @click="clickHandler">{{ buttonText }}</button>
  </div>
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
  emits: ["somebobyJustClickedMe"],
  methods: {
    clickHandler() {
      this.$emit("somebobyJustClickedMe");
    }
  }
};
</script>

<style scoped></style>
