<!-- This is for HTML -->
<template>
  <h1>Welcome to Vue.JS</h1>
  <h3>Is it cool?</h3>
  <OnOffButtons />
  <CountriesList />
  <Images />
</template>

<!-- This is for JS -->
<script>
import OnOffButtons from "./components/OnOffButtons.vue";
import CountriesList from "./components/CountriesList.vue";
import Images from "./components/Images.vue";

export default {
  components: {
    OnOffButtons,
    CountriesList,
    Images,
  },
};
</script>

<!-- This is for CSS -->
<style scoped>
h1 {
  color: red;
}
</style>
