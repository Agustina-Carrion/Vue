<template>
  <TheCounter />
  <br /><br />
  <TheCheckbox />
</template>

<script>
import TheCounter from "./components/TheCounter.vue";
import TheCheckbox from "./components/TheCheckbox.vue";
export default {
  components: { TheCounter, TheCheckbox }
};
</script>

<style scoped></style>
