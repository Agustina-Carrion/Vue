<template>
  <input
    class="input-range"
    type="range"
    @input="inputChange"
    v-model="rangeData"
    :min="minValue"
    :max="maxValue"
  />
</template>

<script>
export default {
  props: {
    minValue: { type: Number, required: true },
    maxValue: { type: Number, required: true },
    valueRead: {
      type: Number,
      required: true
    }
  },
  data() {
    return {
      rangeData: this.valueRead
    };
  },
  watch: {
    valueRead(newValue) {
      this.rangeData = newValue;
    }
  },
  emits: ["sliderChanged"],
  methods: {
    inputChange() {
      this.$emit("sliderChanged", this.rangeData);
    }
  }
};
</script>

<style scoped>
.input-range {
  width: 200px;
  background: #ffffff;
  box-shadow:
    0px 3px 6px rgba(156, 163, 175, 0.35),
    0px 2px 2px rgba(0, 0, 0, 0.06);
  border-radius: 50px;
  cursor: pointer;
  -webkit-appearance: none;
  padding: 8px;
}
input[type="range"]::-webkit-slider-thumb {
  -webkit-appearance: none;
  border: none;
  height: 16px;
  width: 16px;
  border-radius: 50%;
  background: #f08080;
}
</style>
