<script setup>
import heroImage from '../assets/library.jpg'
</script>

<template>
  <div class="inicio">

    <img
      :src="heroImage"
      alt="Biblioteca virtual"
      class="hero-image"
    >

    <h1>📚 Bienvenido/a a BookList SPA</h1>

    <p>
      Explora, organiza y gestiona tu colección de libros favoritos desde una sola aplicación.
    </p>

    <RouterLink
      class="btn"
      to="/libros"
    >
      Ver Biblioteca
    </RouterLink>

  </div>
</template>

<style scoped>
.inicio {
  text-align: center;
  padding: 3rem 2rem;

  display: flex;
  flex-direction: column;
  align-items: center;
}

.hero-image {
  width: 380px;
  max-width: 100%;

  margin-bottom: 2rem;

  filter:drop-shadow(
    0 8px 20px rgba (0, 0, 0, 0.08)
    );
}

h1 {
  color: #5b2c83;
  margin-bottom: 1rem;
}

p {
  margin-bottom: 2rem;
  color: #555;
  font-size: 1.1rem;
}

.btn {
  background-color: #5b2c83;
  color: white;

  padding: 12px 20px;

  border-radius: 8px;
  text-decoration: none;

  transition: 0.2s ease;
}

.btn:hover {
  background-color: #4f46e5;
}
</style>