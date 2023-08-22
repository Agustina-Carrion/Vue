<template>
  <HeaderComponent appName="VueApp" logo="❇️" />
  <ContentComponent title="The Team" />
  <FooterComponent />
</template>

<script>
import HeaderComponent from "./components/HeaderComponent.vue";
import ContentComponent from "./components/ContentComponent.vue";
import FooterComponent from "./components/FooterComponent.vue";

export default {
  components: {
    HeaderComponent,
    ContentComponent,
    FooterComponent,
  },
};
</script>
