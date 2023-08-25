<template>
  <div>
    <h1>Hello</h1>
  </div>
  <PasswordField @passwordOk="handleIt" />
  <div>Password should have between 8 and 14 characters</div>
  <SubmitButton :isDisabled="newValue" />
</template>

<script>
import PasswordField from "./components/PasswordField.vue";
import SubmitButton from "./components/SubmitButton.vue";
export default {
  components: {
    PasswordField,
    SubmitButton
  },
  data() {
    return { newValue: true };
  },
  methods: {
    handleIt(isApproved) {
      // if (isApproved === true) {
      //   this.newValue = false;
      // } else {
      //   this.newValue = true;
      // }
      this.newValue = !isApproved;
    }
  }
};
</script>

<style scoped></style>
