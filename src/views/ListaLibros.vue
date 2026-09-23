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
        type="text"
        placeholder="Título"
      />

      <input
        v-model="nuevoAutor"
        type="text"
        placeholder="Autor"
      />

      <input
        v-model.number="nuevoAnio"
        type="number"
        placeholder="Año"
      />

      <button type="submit">
        ➕ Agregar libro
      </button>
    </form>

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
import Libro from '../components/Libro.vue'

export default {
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
        return
      }

      this.libros.push({
        id: Date.now(),
        titulo: this.nuevoTitulo,
        autor: this.nuevoAutor,
        anio: this.nuevoAnio
      })

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

<style scoped>
h1 {
  color: #5b2c83;
  margin-bottom: 1rem;
}

h2 {
  color: #555;
  font-size: 1.25rem;
}

.container {
  max-width: 900px;
  margin: 2rem auto;
  text-align: center;
}

.formulario {
  display: flex;
  flex-direction: column;
  gap: 10px;

  max-width: 400px;
  margin: 0 auto 2rem;
}

input {
  padding: 10px;
  border-radius: 8px;
  border: 1px solid #ccc;
}

button {
  padding: 10px;
  border-radius: 8px;
  border: none;

  background-color: #42b883;
  color: white;
  cursor: pointer;
}
</style>