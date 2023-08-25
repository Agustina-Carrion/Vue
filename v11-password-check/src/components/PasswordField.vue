<template>
  <input type="password" @input="inputHandler" />
</template>

<script>
export default {
  data() {
    return {
      inputValue: "",
      isApproved: false
    };
  },
  emits: ["passwordOk"],

  methods: {
    inputHandler(event) {
      this.inputValue = event.target.value.length;
      if (this.inputValue >= 8 && this.inputValue <= 14) {
        this.isApproved = true;
        this.$emit("passwordOk", this.isApproved);
      } else {
        this.isApproved = false;
        this.$emit("passwordOk", this.isApproved);
      }
    }
  }
};
</script>

<style scoped></style>
