<template>
  <nav class="navbar">
    <div class="navbar__container">
      <router-link class="navbar__link" to="/">Home</router-link>
      <router-link class="navbar__link" to="/about">About</router-link>
    </div>
  </nav>
</template>

<script>
export default {};
</script>

<style>
.navbar {
  height: 60px;
  width: 100%;
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  background: #2c3e50;
  z-index: 1;
}

.navbar__container {
  width: 80%;
  margin: auto;
  display: flex;
  align-items: center;
  justify-content: flex-end;
}

.navbar__link {
  text-decoration: none;
  border: 2px solid white;
  color: white;
  border-radius: 8px;
  padding: 0.5rem 0.75rem;
  margin: 0.5rem;
}
</style>