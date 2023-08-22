<template>
  <!-- before the update, template required a root tag, now it allows multiple tags as siblings -->
  <div>
    <button>ON</button>
    <button>OFF</button>
  </div>
</template>

<style scoped>
button {
  background-color: yellow;
  margin-right: 20px;
  padding: 10px 20px;
  border: dashed 5px red;
  color: blue;
  border-radius: 20px;
  box-shadow: 10px 10px 10px aliceblue;
}
button:active {
  transform: translateX(5px) translateY(5px);
  box-shadow: none;
}
</style>
