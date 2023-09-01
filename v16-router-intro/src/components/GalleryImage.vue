<template>
  <img :src="imgSrc" />
</template>

<script>
export default {
  props: ["imgSrc"]
};
</script>

<style scoped>
img {
  width: 200px;
  height: 200px;
  border-radius: 15px;
  object-fit: cover;
}
</style>
