<template>
  <div class="card">
    <h3>{{ titulo }}</h3>

    <p>
      <strong>Autor:</strong>
      {{ autor }}
    </p>

    <p>
      <strong>Año:</strong>
      {{ anio }}
    </p>

    <button
      class="btn-eliminar"
      @click="$emit('eliminar')"
    >
      🗑 Eliminar
    </button>
  </div>
</template>

<script>
export default {
  name: 'Libro',

  props: {
    titulo: {
      type: String,
      required: true
    },

    autor: {
      type: String,
      required: true
    },

    anio: {
      type: Number,
      required: true
    }
  },

  emits: ['eliminar']
}
</script>

<style scoped>
.card {
  max-width: 500px;
  margin: 1rem auto;
  padding: 1.5rem;

  border-radius: 12px;
  border: 1px solid #ddd;

  background-color: #f8f8f8;

  box-shadow: 0 2px 6px rgba(0, 0, 0, 0.1);
}

h3 {
  margin-bottom: 1rem;
  color: #4a4a4a;
}

p {
  margin: 0.5rem 0;
}

.btn-eliminar {
  margin-top: 1rem;

  padding: 10px 14px;

  border: none;
  border-radius: 8px;

  background-color: #e74c3c;
  color: white;

  cursor: pointer;

  transition: 0.2s;
}

.btn-eliminar:hover {
  background-color: #c0392b;
}
</style>