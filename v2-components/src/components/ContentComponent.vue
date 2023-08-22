<template>
  <div class="content">
    <h3>{{ title }}</h3>
    <div class="cards">
      <CardComponent
        name="Lola"
        description="Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua."
        :source="'https://picsum.photos/300'"
      />
      <CardComponent
        name="Tina"
        description="Hodor. Hodor hodor, hodor. Hodor hodor hodor hodor hodor. Hodor. Hodor!"
        :source="'https://picsum.photos/250'"
      />
      <CardComponent
        name="John"
        description="Lorem ipsum dolor amet mustache knausgaard +1, blue bottle waistcoat tbh semiotics artisan synth stumptown gastropub."
        :source="'https://picsum.photos/200'"
      />
      <CardComponent
        name="Willy"
        description="Zombie ipsum reversus ab viral inferno, nam rick grimes malum cerebro."
        :source="'https://picsum.photos/400'"
      />
    </div>
  </div>
</template>

<script>
import CardComponent from "./CardComponent.vue";

export default {
  components: { CardComponent },
  props: ["title"],
};
</script>

<style scoped>
.content {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 50px;
}
h3 {
  color: #574ae2;
  text-transform: uppercase;
}

.cards {
  display: flex;
  flex-wrap: wrap;
  gap: 30px;
  justify-content: center;
}

@media (max-width: 768px) {
  .cards {
    gap: 10px;
  }
}
</style>
