<template>
  <h1>This is a gallery</h1>
  <ul class="gallery">
    <GalleryImage v-for="(photo, index) in photos" :key="index" :imgSrc="photo" />
  </ul>
</template>

<script>
import GalleryImage from "../components/GalleryImage.vue";
export default {
  components: {
    GalleryImage
  },
  data() {
    return {
      photos: [
        "https://picsum.photos/200/300",
        "https://picsum.photos/400",
        "https://picsum.photos/350"
      ]
    };
  }
};
</script>

<style scoped>
.gallery {
  display: flex;
  gap: 50px;
}
</style>
