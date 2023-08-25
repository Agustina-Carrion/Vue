<template>
  <div>
    <input type="password" @input="inputChanged" v-model="passwordData" />
  </div>
  <div v-if="!isValid">password should have between 8 and 14 characters</div>
</template>

<script>
export default {
  emits: ["inputChange"],
  props: { passwordValue: { type: String } },
  data() {
    return {
      isValid: false,
      passwordData: this.passwordValue,
    };
  },
  watch: {
    passwordValue() {
      this.passwordData = this.passwordValue;
    },
  },
  methods: {
    inputChanged() {
      if (this.passwordData.length >= 8 && this.passwordData.length <= 14) {
        this.isValid = true;
      } else {
        this.isValid = false;
      }
      this.$emit("inputChange", this.isValid);
    },
  },
};
</script>

<style scoped></style>
