<template>
  <div class="card">
    <h3>{{ titulo }}</h3>
    <p><strong>Autor:</strong> {{ autor }}</p>
    <p><strong>Año:</strong> {{ anio }}</p>
  </div>
</template>

<script>
export default {
  name: 'Libro',

  props: {
    titulo: String,
    autor: String,
    anio: Number
  }
}
</script>

<style scoped>
.card {
  border: 1px solid #ddd;
  border-radius: 10px;
  padding: 1rem;
  margin: 1rem auto;
  max-width: 500px;
  background-color: #f8f8f8;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}
</style>