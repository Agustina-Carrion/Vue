<template>
  <section>
    <h1>{{ title }}</h1>
    <TheList />
  </section>
</template>

<script>
import TheList from "./TheList.vue";
export default {
  components: {
    TheList
  },
  props: ["title"]
};
</script>

<style scoped>
section {
  display: flex;
  flex-direction: column;
  gap: 20px;
  justify-content: center;
  align-items: start;
  margin: 0 50px
}
</style>
