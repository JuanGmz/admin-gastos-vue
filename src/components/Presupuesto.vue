<script setup>
    import { ref } from 'vue'
    import Alerta from './Alerta.vue'

    // States
    const presupuesto = ref(0)
    const error = ref('')

    // Macros
    const emit = defineEmits(['definir-presupuesto'])

    // Funciones
    const definirPresupuesto = () => {
        if (presupuesto.value <= 0) {
            error.value = 'Presupuesto no válido'

            // Reiniciar el state de error para que se deje de mostrar la alerta
            setTimeout(() => {
                error.value = ''
            }, 3000);

            return
        }

        emit('definir-presupuesto', presupuesto.value)
    }
</script>

<template>
    <form 
        class="presupuesto"
        @submit.prevent="definirPresupuesto"
    >
        <!-- Alerta usando Slots-->
        <Alerta v-if="error">
            {{ error }}
        </Alerta>

        <div class="campo">
            <label for="">Definir Presupuesto</label>

            <input
                id="nuevo-presupuesto"
                class="nuevo-presupuesto"
                placeholder="Añade tu presupuesto"    
                type="number"
                v-model.number="presupuesto"
            >
        </div>

        <input type="submit" value="Definir Presupuesto">
    </form>
</template>

<style scoped>
    .presupuesto {
        width: 100%;
    }

    .campo {
        display: grid;
        gap: 2rem;
    }

    .presupuesto label {
        font-size: 2.8rem;
        text-align: center;
        color: var(--blue);
    }

    .presupuesto input[type="number"] {
        background-color: var(--light-gray);
        border-radius: 1rem;
        padding: 1rem;
        border: none;
        font-size: 2.2rem;
        text-align: center;
    }

    .presupuesto input[type="submit"] {
        background-color: var(--blue);
        border: none;
        padding: 1rem;
        text-align: center;
        font-size: 2rem;
        margin-top: 2rem;
        color: var(--white);
        font-weight: 900;
        width: 100%;
        transition: background-color 300ms ease;
    }

    .presupuesto input[type="submit"]:hover {
        background-color: #1048A4;
        cursor: pointer;
    }
</style>