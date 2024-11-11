<script setup>
    import imagen from '../assets/img/grafico.jpg'
</script>

<template>
    <div class="dos-columnas">
        <div class="contenedor-grafico">
            <img :src="imagen" alt="Gráfico">
        </div>
        
        <div class="contenedor-presupuesto">
            <button class="reset-app">Resetear App</button>

            <p>
                <span>Presupuesto: </span>
                $0
            </p>

            <p>
                <span>Disponible: </span>
                $0
            </p>

            <p>
                <span>Gastado: </span>
                $0
            </p>
        </div>
    </div>
</template>

<style scoped>
    .dos-columnas {
        display: flex;
        flex-direction: column;
    }

    .dos-columnas>:first-child {
        margin-bottom: 3rem;
    }

    @media (min-width: 768px) {
        .dos-columnas {
            flex-direction: row;
            gap: 4rem;
            align-items: center;
        }

        .dos-columnas>:first-child {
        margin-bottom: 0;
        }
    }

    .contenedor-presupuesto {
        width: 100%;
    }

    .contenedor-presupuesto p {
        font-size: 2.4rem;
        text-align: center;
        color: var(--dark-gray);
    }

    @media (min-width: 768px) {
        .contenedor-presupuesto p {
        text-align: left;
        }
    }

    .contenedor-presupuesto span {
        font-weight: 900;
        color: var(--blue);
    }

    .reset-app {
        background-color: #DB2777;
        border: none;
        padding: 1rem;
        width: 100%;
        color: var(--white);
        font-weight: 900;
        text-transform: uppercase;
        border-radius: 1rem;
        transition: background-color 300ms ease;
    }

    .reset-app:hover {
        background-color: #C11D67;
        cursor: pointer;
    }
</style>