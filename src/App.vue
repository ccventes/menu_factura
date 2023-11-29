<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from './components/HelloWorld.vue'
</script>

<template>
  <h1>Hola mundo</h1>
  <div class="image-container">
  <!-- Inserta tus URLs de imágenes aquí -->
  <img src="./images/imagen1.jpg" alt="Imagen 1">
  <img src="./images/imagen2.jpg" alt="Imagen 2">
  <img src="./images/imagen3.jpg" alt="Imagen 3">
  <!-- Añade más imágenes según sea necesario -->
</div>
</template>

<style scoped>
.image-container {
      display: flex;
      width: 10vw; /* El 20% del ancho de la ventana gráfica */
      height: auto; /* Altura automática para mantener la proporción original */
      
      justify-content: center;
      align-items: center;
      height: 20vh; /* O ajusta según tus necesidades */
    }

.image-container img {
      max-width: 100%;
      height: auto;
      margin-right: 10px; /* Espacio entre las imágenes */
}

header {
  line-height: 1.5;
  max-height: 100vh;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

nav {
  width: 100%;
  font-size: 12px;
  text-align: center;
  margin-top: 2rem;
}

nav a.router-link-exact-active {
  color: var(--color-text);
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}

nav a:first-of-type {
  border: 0;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  nav {
    text-align: left;
    margin-left: -1rem;
    font-size: 1rem;

    padding: 1rem 0;
    margin-top: 1rem;
  }
}
</style>
