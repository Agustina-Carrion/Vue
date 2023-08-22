<template>
  <div>
    <TheCounter />
    <TheSwitcher />
  </div>
</template>

<script>
import TheCounter from "./components/TheCounter.vue";
import TheSwitcher from "./components/TheSwitcher.vue";
export default {
  components: { TheCounter, TheSwitcher }
};
</script>

<style scoped></style>
