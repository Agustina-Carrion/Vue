<template>
  <input class="input-number" type="number" @input="inputChange" v-model="inputData" />
</template>

<script>
export default {
  props: {
    valueRead: {
      type: Number,
      required: true
    }
  },
  data() {
    return {
      inputData: this.valueRead
    };
  },
  watch: {
    valueRead(newValue) {
      this.inputData = newValue;
    }
  },
  emits: ["valueChanged"],
  methods: {
    inputChange() {
      this.$emit("valueChanged", this.inputData);
    }
  }
};
</script>

<style scoped>
.input-number {
  width: 25px;
  text-align: center;
  padding: 8px;
  background: #ffffff;
  box-shadow:
    0px 3px 6px rgba(156, 163, 175, 0.35),
    0px 2px 2px rgba(0, 0, 0, 0.06);
  border-radius: 50px;
  border: none;
}
input::-webkit-outer-spin-button,
input::-webkit-inner-spin-button {
  -webkit-appearance: none;
  margin: 0;
}
</style>
