<template>
  <li class="nav-item">
    <a :href="path" class="nav-link">
      {{ title }}
      <span class="icon">{{ icon }}</span>
    </a>
  </li>
</template>

<script>
export default {
  props: ["title", "path", "icon"],
};
</script>

<style scoped>
.nav-item {
  list-style: none;
  margin: 0;
  padding: 0;
}

.nav-link {
  text-decoration: none;
  color: #011936;
  font-size: 20px;
  padding: 10px;
  display: flex;
  align-items: center;
}

.icon {
  margin-left: 5px;
  white-space: nowrap;
}

.nav-link:hover {
  font-weight: bold;
  color: #574ae2;
}
</style>
