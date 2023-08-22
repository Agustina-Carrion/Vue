<template>
  <div class="switcher">
    <h2>Switch between counters:</h2>
    <input type="checkbox" v-model="isChecked" />
  </div>
  <div class="counter">
    <h3>Count 1:</h3>
    <div>{{ counter }}</div>
  </div>
  <div class="counter">
    <h3>Count 2:</h3>
    <div>{{ counter2 }}</div>
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
      counter: 0,
      counter2: 0,
      isChecked: false
    };
  },
  methods: {
    upHandler() {
      if (this.isChecked) {
        this.counter2++;
      } else {
        this.counter++;
      }
    },
    downHandler() {
      if (this.isChecked) {
        this.counter2--;
      } else {
        this.counter--;
      }
    },
    resetHandler() {
      if (this.isChecked) {
        this.counter2 = 0;
      } else {
        this.counter = 0;
      }
    }
  }
};
</script>

<style scoped>
.switcher {
  display: flex;
}

</style>
