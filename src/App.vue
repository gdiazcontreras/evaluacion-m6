<template>
  <div class="app">
    <nav>
      <RouterLink to="/">
        🏠 Inicio
      </RouterLink>

      <RouterLink to="/libros">
        📚 Libros
      </RouterLink>
    </nav>

    <RouterView />
  </div>
</template>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  background-color: #f5f5f5;
  font-family: Arial, sans-serif;
}

nav {
  padding: 20px;
  background-color: #42b883;

  display: flex;
  justify-content: center;
  gap: 20px;
}

nav a {
  color: white;
  text-decoration: none;
  font-weight: bold;
}

nav a.router-link-active {
  text-decoration: underline;
}

.app {
  min-height: 100vh;
}
</style>