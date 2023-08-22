<template>
  <div class="nav-bar">
    <div class="app-name">
      <span>{{ logo }}</span>
      <h1>{{ appName }}</h1>
    </div>
    <ul>
      <!-- v-for is a directive to render a list of items based on an array -->
      <NavBarItem
        v-for="item in items"
        :key="item.title"
        :title="item.title"
        :path="item.path"
        :icon="item.icon"
      />
    </ul>
  </div>
</template>

<script>
import NavBarItem from "./NavBarItem.vue";

export default {
  components: { NavBarItem },
  props: ["appName", "logo"],
  data() {
    return {
      items: [
        { title: "Home", path: "", icon: "🏠" },
        { title: "About", path: "", icon: "🙋🏻‍♀️" },
        { title: "Contact", path: "", icon: "📲" },
      ],
    };
  },
};
</script>

<style scoped>
.nav-bar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 20px;
  margin: 10px;
}
.app-name {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 10px;
}
h1 {
  font-weight: bold;
}
ul {
  display: flex;
  list-style: none;
  padding: 0;
  gap: 20px;
}
</style>
