<template>
  <header>
    <nav>
      <RouterLink to="/" class="nav-link">Home</RouterLink>
      <RouterLink to="/about" class="nav-link">About</RouterLink>
      <RouterLink to="/gallery" class="nav-link">Gallery</RouterLink>
    </nav>
  </header>
  <RouterView />
</template>

<script>
export default {};
</script>

<style scoped>
header {
  position: sticky;
  height: 50px;
  padding: 20px;
  display: flex;
  justify-content: start;
  align-items: center;
}

nav {
  display: flex;
  gap: 10px;
}

.nav-link {
  border: solid 2px black;
  text-transform: uppercase;
  text-decoration: none;
  color: black;
  width: 100px;
  height: 30px;
  display: flex;
  justify-content: center;
  align-items: center;
}

.nav-link:hover {
  background-color: #333;
  color: #fff;
}
</style>
