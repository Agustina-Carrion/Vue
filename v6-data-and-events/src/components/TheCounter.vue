<template>
  <div>Counter: {{ counter }}</div>
  <div class="counterButtons">
    <button @click="upHandler">Go Up</button>
    <button @click="downHandler">Go Down</button>
    <button @click="resetHandler">Reset</button>
    <!-- another way of doing it without methods -->
    <!-- <button @click="counter++">Go Up</button>
    <button @click="counter--">Go Down</button>
    <button @click="counter = 0">Reset</button> -->
  </div>
</template>

<script>
export default {
  data() {
    return {
      counter: 0
    };
  },
  methods: {
    upHandler() {
      // this. will allow to access the variable created in data
      this.counter += 1;
    },
    downHandler() {
      this.counter -= 1;
    },
    resetHandler() {
      this.counter = 0;
    }
  }
};
</script>

<style scoped>
.counterButtons {
  display: flex;
  gap: 20px;
  margin: 10px 0;
}
</style>
