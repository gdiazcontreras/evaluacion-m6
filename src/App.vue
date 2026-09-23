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
  background-color: #ffffff;
  font-family: Arial, sans-serif;
  color: #333;
}

nav {
  padding: 20px;
  background-color: #5b2c83;
  border-bottom: 1px solid #e5e7eb;

  display: flex;
  justify-content: center;
  gap: 20px;
}

nav a {
  color: white;
  font-weight: bold;
  text-decoration: none;
  transition: 0.2s ease;
}

nav a.router-link-active {
color: white;
border-bottom: 2px solid white;
padding-bottom: 4px;
}

nav a:hover {
  opacity: 0.8;
}

.app {
  min-height: 100vh;
}
</style>