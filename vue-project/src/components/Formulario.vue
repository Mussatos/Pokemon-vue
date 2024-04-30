<script setup>
import { ref } from 'vue'

const emit = defineEmits(["salva-pessoa"])

const nome = ref('')
const cpf = ref('')
const categoria = ref('')

const onSubmit = () => {
    emit('salva-pessoa', nome, cpf, categoria)
}

</script>

<template>

    <form @submit.prevent="onSubmit">
        <div>
            <label for="nome">Nome</label>
            <input v-model="nome" type="text" id="nome">
        </div>

        <div>
            <label for="cpf">CPF</label>
            <input v-model="cpf" type="text" id="cpf">
        </div>

        <div>
            <label for="categoria">categoria</label>
            <input v-model="categoria" type="text" id="categoria">
        </div>

        <button>Salvar</button>


    </form>
</template>