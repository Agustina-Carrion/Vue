<template>
  <div class="switcher">
    <h2>Switch between counters:</h2>
    <!-- <input type="checkbox" v-model="isCheckedCounter1" />
    <input type="checkbox" v-model="isCheckedCounter2" /> -->
  </div>
  <div class="display-box">
    <TheCheckbox @change="handleChange1" />
    <DisplayCounter label="Counter 1" :valueToShow="counter1" />
    <TheCheckbox @change="handleChange2" />
    <DisplayCounter label="Counter 2" :valueToShow="counter2" />
  </div>
  <ButtonBox @buttonClicked="handleClick" />
</template>

<script>
import DisplayCounter from "./DisplayCounter.vue";
import ButtonBox from "./ButtonBox.vue";
import TheCheckbox from "./TheCheckbox.vue";

export default {
  components: { DisplayCounter, ButtonBox, TheCheckbox },
  data() {
    return {
      isCheckedCounter1: false,
      isCheckedCounter2: false,
      counter1: 0,
      counter2: 0
    };
  },
  methods: {
    handleChange1(value) {
      this.isCheckedCounter1 = value;
    },
    handleChange2(value) {
      this.isCheckedCounter2 = value;
    },
    handleClick(value) {
      if (this.isCheckedCounter1 && this.isCheckedCounter2) {
        this.counter1 += value;
        this.counter2 += value;
      } else if (this.isCheckedCounter2) {
        this.counter2 += value;
      } else if (this.isCheckedCounter1) {
        this.counter1 += value;
      }

      if (value === 0) {
        this.counter1 = 0;
        this.counter2 = 0;
      }
    }
  }
};
</script>

<style scoped>
.switcher {
  display: flex;
  margin-top: 50px;
}
.display-box {
  display: flex;
  gap: 20px;
}
</style>
