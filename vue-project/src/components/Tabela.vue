<script setup>

import Linha from "./Linha.vue"

const props = defineProps(["lista"])

</script>


<template>

    <table>
        <th>Nome</th>
        <th>CPF</th>
        <th>Categoria</th>
        <th>Ações</th>

    </table>

        <tbody>

            <Linha v-for="pokemon in lista"
            :pokemon="pokemon"/>

        </tbody>

</template>