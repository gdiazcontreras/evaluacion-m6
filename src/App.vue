<template>
  <div class="container">
    <h1>📚 Biblioteca Virtual</h1>

    <p v-if="libros.length > 0">
      Hay {{ libros.length }} libros disponibles
    </p>

    <p v-else>
      No hay libros disponibles
    </p>

    <button @click="mostrarLista = !mostrarLista">
      {{ mostrarLista ? 'Ocultar libros' : 'Mostrar libros' }}
    </button>

    <div v-show="mostrarLista">
      <Libro
        v-for="libro in libros"
        :key="libro.id"
        :titulo="libro.titulo"
        :autor="libro.autor"
        :anio="libro.anio"
      />
    </div>
  </div>
</template>

<script>
import Libro from './components/Libro.vue'

export default {
  name: 'App',

  components: {
    Libro
  },

  data() {
    return {
      mostrarLista: true,

      libros: [
        {
          id: 1,
          titulo: 'Cien años de soledad',
          autor: 'Gabriel García Márquez',
          anio: 1967
        },
        {
          id: 2,
          titulo: 'El Principito',
          autor: 'Antoine de Saint-Exupéry',
          anio: 1943
        },
        {
          id: 3,
          titulo: '1984',
          autor: 'George Orwell',
          anio: 1949
        }
      ]
    }
  }
}
</script>

<style>
.container {
  max-width: 900px;
  margin: 2rem auto;
  text-align: center;
  font-family: Arial, sans-serif;
}

h1 {
  color: #42b883;
}

button {
  margin: 1rem 0;
  padding: 0.8rem 1.2rem;
  border: none;
  border-radius: 8px;
  background-color: #42b883;
  color: white;
  cursor: pointer;
  font-size: 1rem;
}

button:hover {
  background-color: #369870;
}
</style>