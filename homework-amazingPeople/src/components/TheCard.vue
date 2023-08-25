<template>
  <li class="card">
    <div class="presentation">
      <img :src="imgSrc" />
      <div>
        <h2>{{ name }}</h2>
        <h4>{{ role }}</h4>
      </div>
    </div>
    <p>{{ description }}</p>
    <a :href="path">More</a>
  </li>
</template>

<script>
export default {
  props: {
    imgSrc: { type: String },
    name: { type: String },
    role: { type: String },
    description: { type: String },
    path: { type: String }
  }
};
</script>

<style scoped>
.card {
  display: flex;
  flex-direction: column;
  gap: 5px;
  padding: 20px;
  width: 250px;
  min-height: 150px;
  border: solid 2px black;
}
img {
  object-fit: cover;
  width: 100px;
  height: 100px;
  border-radius: 50%;
}
.presentation {
  display: flex;
  gap: 20px;
}
</style>
