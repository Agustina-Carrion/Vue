<template>
  <div>
    <h1>Hello</h1>
  </div>
  <PasswordField
    @inputChange="passwordChanged"
    :passwordValue="passwordValue"
  />
  <SubmitButton :isDisabled="isDisabled" />
  <ResetButton @resetPassword="passwordReset" />
</template>

<script>
import PasswordField from "./components/PasswordField.vue";
import SubmitButton from "./components/SubmitButton.vue";
import ResetButton from "./components/ResetButton.vue";

export default {
  components: {
    PasswordField,
    SubmitButton,
    ResetButton,
  },
  data() {
    return {
      isDisabled: true,
      passwordValue: "",
    };
  },
  methods: {
    passwordChanged(isValid) {
      this.isDisabled = !isValid;
    },
    passwordReset() {
      this.passwordValue = "";
    },
  },
};
</script>

<style scoped></style>
