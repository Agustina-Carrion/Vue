<template>
  <button :disabled="isDisabled">Submit</button>
</template>

<script>
export default {
  props: { isDisabled: { type: Boolean } }
};
</script>

<style scoped></style>
