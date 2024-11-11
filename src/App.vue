<script setup>
  import { ref } from 'vue'
  import Presupuesto from './components/Presupuesto.vue'
  import ControlPresupuesto from './components/ControlPresupuesto.vue'

  // States
  const presupuesto = ref(0)

  // Funciones
  const definirPresupuesto = (cantidad) => {
    presupuesto.value = cantidad
  }
</script>

<template>
  <div>
    <header>
      <h1>Planificador de Gastos</h1>

      <div class="contenedor-header contenedor sombra">
        <Presupuesto 
          v-if="presupuesto === 0"
          @definir-presupuesto="definirPresupuesto"
        />

        <ControlPresupuesto
          v-else
        />
      </div>
    </header>
  </div>
</template>

<style>
  :root {
    --blue: #3B82F6;
    --white: #FFFFFF;
    --light-gray: #F5F5F5;
    --gray: #94A3B8;
    --dark-gray: #64768B;
    --black: #000000;
  }

  html {
    font-size: 62.5%;
    box-sizing: border-box;
  }

  *,
  *::before,
  *::after {
    box-sizing: inherit;
  }

  body {
    font-size: 1.6rem;
    font-family: "Lato", sans-serif;
    background-color: var(--light-gray);
  }

  h1 {
    font-size: 4rem;
  }

  h2 { 
    font-size: 2rem;
  }

  header {
    background-color: var(--blue);
  }

  header h1 {
    padding: 3rem 0;
    margin: 0;
    color: var(--white);
    text-align: center;
  }

  .contenedor {
    width: 90%;
    max-width: 80rem;
    margin: 0 auto;
  }

  .contenedor-header {
    margin-top: -5rem;
    transform: translateY(5rem);
    padding: 5rem;
  }

  .sombra {
    box-shadow: 0px 10px 15px -3px rgba(0, 0, 0, 0.1);
    background-color: var(--white);
    border-radius: 1.2rem;
    padding: 5rem;
  }
</style>