<template>
  <div class="detalle">
    <h1>📖 Detalle del Libro</h1>

    <h2>ID: {{ id }}</h2>
  </div>
</template>

<script>
export default {
  props: ['id']
}
</script>

<style scoped>
.detalle {
  text-align: center;
  padding: 3rem;
}
</style>
