<script setup>
import Tabela from "./components/Tabela.vue"
import Formulario from "./components/Formulario.vue"

import {ref, onMounted} from 'vue'

const lista = ref([])

onMounted(() => {

  fetch("https://pokeapi.co/api/v2/pokemon").then(result => result.json()).then(console.log)

})

const evento = (nome, cpf, categoria) =>{

  const item = {nome, cpf, categoria};
  
  lista.value.push(item);

}

</script>

<template>
  <main>

      <Formulario @salva-pessoa="evento"/>
      <Tabela :pokemon="lista"/>

  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
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
}
</style>
