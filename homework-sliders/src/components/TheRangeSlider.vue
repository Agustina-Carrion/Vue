<template>
  <div class="range-slider">
    <TheSlider
      :minValue="0"
      :maxValue="100"
      @sliderChanged="handleSlider"
      :valueRead="Number(inputData)"
    />
    <TheInput @valueChanged="handleInput" :valueRead="Number(inputData)" />
  </div>
</template>

<script>
import TheInput from "./TheInput.vue";
import TheSlider from "./TheSlider.vue";
export default {
  components: { TheInput, TheSlider },
  props: ["sliderNumber"],
  data() {
    return { inputData: 0 };
  },
  emits: ["valueData"],
  methods: {
    handleSlider(value) {
      this.inputData = value;
      this.$emit("valueData", { index: this.sliderNumber - 1, value: Number(this.inputData) });
    },
    handleInput(value) {
      this.inputData = value;
      this.$emit("valueData", { index: this.sliderNumber - 1, value: Number(this.inputData) });
    }
  }
};
</script>

<style scoped>
.range-slider {
  display: flex;
  gap: 20px;
  justify-content: center;
  align-items: center;
}
</style>
