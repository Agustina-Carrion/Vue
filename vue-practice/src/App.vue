<template>
  <div>
    <TheCounter />
    <TheSwitcher />
    <CheckboxSwitcher />
  </div>
</template>

<script>
import TheCounter from "./components/TheCounter.vue";
import TheSwitcher from "./components/TheSwitcher.vue";
import CheckboxSwitcher from "./components/CheckboxSwitcher.vue";
export default {
  components: { TheCounter, TheSwitcher, CheckboxSwitcher }
};
</script>

<style scoped></style>
