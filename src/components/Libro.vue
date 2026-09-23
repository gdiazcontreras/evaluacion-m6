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
  props: {
    titulo: String,
    autor: String,
    anio: Number
  },

  emits: ['eliminar']
}
</script>

<style scoped>
.card {
  background-color: white;
  margin: 1rem auto;
  padding: 1.5rem;
  max-width: 500px;

  border-radius: 12px;

  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
}

h3 {
  margin-bottom: 1rem;
}

p {
  margin: 0.5rem 0;
}

.btn-eliminar {
  margin-top: 1rem;

  padding: 10px 16px;

  border: none;
  border-radius: 8px;

  background-color: #ef4444;
  color: white;

  font-size: 1rem;
  font-weight: 500;

  cursor: pointer;

  transition: 0.2s ease;
}

.btn-eliminar:hover {
  background-color: #dc2626;
  transform: translateY(-1px);
}
</style>