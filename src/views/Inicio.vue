<template>
  <div class="inicio">
    <h1>📚 Bienvenida a BookList SPA</h1>

    <p>
      Gestiona tu colección de libros favoritos.
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
  padding: 4rem 2rem;
}

h1 {
  margin-bottom: 1rem;
  color: #42b883;
}

p {
  margin-bottom: 2rem;
}

.btn {
  background-color: #42b883;
  color: white;
  text-decoration: none;

  padding: 12px 20px;
  border-radius: 8px;
}
</style>