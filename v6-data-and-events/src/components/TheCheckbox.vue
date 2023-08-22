<template>
  <input type="checkbox" v-model="isChecked" />
  <div>The checkbox is on: {{ isChecked }}</div>

  <button @click="isChecked = false">Back to false</button>
</template>

<script>
export default {
  data() {
    return {
      isChecked: false
    };
  }
};
</script>

<style scoped></style>
