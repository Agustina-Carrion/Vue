<template>
  <div class="switcher">
    <h2>Activate</h2>
    <div class="selector">
      <h3>Counter 1</h3>
      <input type="radio" v-model="selectedCounter" value="counter1" />
    </div>
    <div class="selector">
      <h3>Counter 2</h3>
      <input type="radio" v-model="selectedCounter" value="counter2" />
    </div>
  </div>
  <div class="counter">
    <h3>Selected counter count:</h3>
    <div>{{ currentCounter }}</div>
  </div>
  <div class="handlers">
    <button @click="upHandler">Up</button>
    <button @click="resetHandler">Reset</button>
    <button @click="downHandler">Down</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      selectedCounter: "counter1",
      counter1: 0,
      counter2: 0
    };
  },
  computed: {
    currentCounter() {
      return this.selectedCounter === "counter1" ? this.counter1 : this.counter2;
    }
  },
  methods: {
    upHandler() {
      if (this.selectedCounter === "counter1") {
        this.counter1++;
      } else {
        this.counter2++;
      }
    },
    resetHandler() {
      if (this.selectedCounter === "counter1") {
        this.counter1 = 0;
      } else {
        this.counter2 = 0;
      }
    },
    downHandler() {
      if (this.selectedCounter === "counter1") {
        this.counter1--;
      } else {
        this.counter2--;
      }
    }
  }
};
</script>

<style scoped>
.switcher {
  display: flex;
  gap: 20px;
  margin-top: 50px;
}
.selector {
  display: flex;
  align-items: center;
  gap: 5px;
}
</style>
