<template>
  <h1>Hello lovely images!</h1>
  <div>
    <img src="https://picsum.photos/600" alt="Random image" />
    <img src="https://picsum.photos/400" alt="Random image" />
    <img src="https://picsum.photos/200" alt="Random image" />
  </div>
</template>

<style scoped>
div {
  display: flex;
  gap: 50px;
}
img {
  width: 250px;
  height: auto;
}
</style>
