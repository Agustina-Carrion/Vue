<template>
  <div class="card">
    <h4>{{ name }}</h4>
    <p>{{ description }}</p>
    <img :src="source" />
  </div>
</template>

<script>
export default {
  props: ["name", "description", "source"],
};
</script>

<style scoped>
.card {
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 200px;
  padding: 10px;
  border: 1px solid black;
  border-radius: 10px;
  box-shadow: 0 8px 16px rgba(0, 0, 0, 0.3);
}

h4,
p {
  margin: 5px 0;
}

p {
  font-size: 12px;
  text-align: center;
  flex-grow: 1;
  display: -webkit-box;
  -webkit-box-orient: vertical;
  overflow: hidden;
  line-height: 1.2;
  -webkit-line-clamp: 2;
}

img {
  width: 150px;
  height: 150px;
  border-radius: 50%;
  object-fit: cover;
}
</style>
