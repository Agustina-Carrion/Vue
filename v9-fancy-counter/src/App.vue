<template>
  <div class="counter">
    <DisplayCounter :valueToShow="counter" />
    <ButtonBox @oneOfTheButtonsWasClicked="handleIt" />
  </div>
</template>

<script>
import ButtonBox from "./components/ButtonBox.vue";
import DisplayCounter from "./components/DisplayCounter.vue";
export default {
  components: {
    ButtonBox,
    DisplayCounter
  },
  data() {
    return {
      counter: 0
    };
  },
  methods: {
    //value is the second argument passed in the emitter
    handleIt(value) {
      if (value === 0) {
        this.counter = 0;
      } else {
        this.counter += value;
      }
    }
  }
};
</script>

<style scoped>
.counter {
  display: flex;
  flex-direction: column;
  gap: 50px;
  justify-content: center;
  align-items: center;
}
</style>
