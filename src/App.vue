<template>
  <div class="container">
    <h1>📚 BookList SPA</h1>

    <p>Hola, {{ nombre }}</p>

    <h2>Contador: {{ contador }}</h2>

    <button @click="incrementar">
      Incrementar
    </button>
  </div>
</template>

<script>
export default {
  name: 'App',

  data() {
    return {
      nombre: 'Gabriela',
      contador: 0
    }
  },

  methods: {
    incrementar() {
      this.contador++
    }
  }
}
</script>

<style>
.container {
  text-align: center;
  margin-top: 50px;
  font-family: Arial, sans-serif;
}

button {
  padding: 10px 20px;
  cursor: pointer;
  border: none;
  border-radius: 8px;
  background-color: #42b883;
  color: white;
}

button:hover {
  background-color: #369870;
}
</style>