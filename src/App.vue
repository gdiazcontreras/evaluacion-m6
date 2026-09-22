<template>
  <div class="container">
    <h1>📚 Biblioteca Virtual</h1>

    <form
      class="formulario"
      @submit.prevent="agregarLibro"
    >
      <h2>Agregar libro</h2>

      <input
        v-model="nuevoTitulo"
        @keyup.enter="agregarLibro"
        type="text"
        placeholder="Título del libro"
      />

      <input
        v-model="nuevoAutor"
        @keyup.enter="agregarLibro"
        type="text"
        placeholder="Autor"
      />

      <input
        v-model.number="nuevoAnio"
        @keyup.enter="agregarLibro"
        type="number"
        placeholder="Año"
      />

      <button type="submit">
        ➕ Agregar libro
      </button>
    </form>

    <hr />

    <p v-if="libros.length > 0">
      Hay {{ libros.length }} libros disponibles
    </p>

    <p v-else>
      No hay libros disponibles
    </p>

    <Libro
      v-for="libro in libros"
      :key="libro.id"
      :titulo="libro.titulo"
      :autor="libro.autor"
      :anio="libro.anio"
      @eliminar="eliminarLibro(libro.id)"
    />
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
      ],

      nuevoTitulo: '',
      nuevoAutor: '',
      nuevoAnio: ''
    }
  },

  methods: {
    agregarLibro() {
      if (
        !this.nuevoTitulo ||
        !this.nuevoAutor ||
        !this.nuevoAnio
      ) {
        alert('Por favor completa todos los campos')
        return
      }

      const nuevoLibro = {
        id: Date.now(),
        titulo: this.nuevoTitulo,
        autor: this.nuevoAutor,
        anio: this.nuevoAnio
      }

      this.libros.push(nuevoLibro)

      this.nuevoTitulo = ''
      this.nuevoAutor = ''
      this.nuevoAnio = ''
    },

    eliminarLibro(id) {
      this.libros = this.libros.filter(
        libro => libro.id !== id
      )
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
  margin-bottom: 1.5rem;
}

.formulario {
  display: flex;
  flex-direction: column;
  gap: 12px;
  max-width: 400px;
  margin: 0 auto 2rem;
}

input {
  padding: 12px;
  border: 1px solid #ccc;
  border-radius: 8px;
  font-size: 1rem;
}

button {
  padding: 12px;
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

hr {
  margin: 2rem 0;
}
</style>