<template>
  <div class="display-holder">
    <h4>{{ label }}</h4>
    <div class="display-value">{{ valueToShow }}</div>
  </div>
</template>

<script>
export default {
  props: {
    label: { type: String, required: false },
    valueToShow: { type: Number, required: true }
  }
};
</script>

<style scoped>
.display-holder {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding: 20px;
}
.display-value {
  width: 50px;
  min-height: 50px;
  background-color: #ccc;
  border-radius: 15%;
  margin: 20px 0 20px 0;
  font-weight: bold;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
