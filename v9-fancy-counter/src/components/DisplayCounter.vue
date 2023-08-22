<template>
  <div>{{ valueToShow }}</div>
</template>

<script>
export default {
  props: {
    valueToShow: { type: Number, required: true }
  }
};
</script>

<style scoped>
div {
  background-color: #ccc;
  min-height: 200px;
  width: 200px;
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 50px;
  border-radius: 15%;
}
</style>
