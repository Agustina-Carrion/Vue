<template>
  <div class="box-sliders">
    <TheRangeSlider @valueData="updateCounter" :sliderNumber="1" />
    <TheRangeSlider @valueData="updateCounter" :sliderNumber="2" />
    <TheRangeSlider @valueData="updateCounter" :sliderNumber="3" />
    <TheRangeSlider @valueData="updateCounter" :sliderNumber="4" />
    <TheRangeSlider @valueData="updateCounter" :sliderNumber="5" />
    <div>{{ counter }} / 500</div>
    <!-- <button @click="updateCounter">Sum Up</button> -->
  </div>
</template>

<script>
import TheRangeSlider from "./components/TheRangeSlider.vue";
export default {
  components: { TheRangeSlider },
  data() {
    return {
      counter: 0,
      sliderValues: [0, 0, 0, 0, 0]
      // temp1: 0,
      // temp2: 0,
      // temp3: 0,
      // temp4: 0,
      // temp5: 0
    };
  },
  methods: {
    updateCounter({ index, value }) {
      const previousValue = this.sliderValues[index];
      const totalSum = this.counter - previousValue + value;
      if (totalSum <= 500) {
        this.counter = totalSum;
        this.sliderValues[index] = value;
      }
    }
    // updateCounter1(value) {
    //   this.temp1 = value;
    // },
    // updateCounter2(value) {
    //   this.temp2 = value;
    // },
    // updateCounter3(value) {
    //   this.temp3 = value;
    // },
    // updateCounter4(value) {
    //   this.temp4 = value;
    // },
    // updateCounter5(value) {
    //   this.temp5 = value;
    // },
    // updateCounter() {
    //   this.counter = this.temp1 + this.temp2 + this.temp3 + this.temp4 + this.temp5;
    // }
  }
};
</script>

<style scoped>
.box-sliders {
  width: 600px;
  height: 600px;
  background-color: #f4f3ee;
  border-radius: 15px;
  display: flex;
  flex-direction: column;
  gap: 40px;
  justify-content: center;
  align-items: center;
}
</style>
