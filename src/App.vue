<script setup>

</script>

<template>
  <div>
    <header>
      <h1>Planificador de Gastos</h1>
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
</style>