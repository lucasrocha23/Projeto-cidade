<script setup>
import Home from './paginas/Home.vue'
import Locais from './paginas/Locais.vue'
import {ref, provide} from 'vue'

const cidade = ref({})
const paginaAtual = ref(0)
const paginas = [
  {label: 'Home', comp: Home},
  {label: 'Locais', comp: Locais}
]

fetch('src/assets/dadosCidade.json')
  .then(res => res.json())
  .then(data => cidade.value = data)
  .catch()
</script>

<template>
  <header>
    <div class="nav-bar"><a v-for="(pagina, index) in paginas" :key="`pagina.label` + index" @click="paginaAtual = index">
      {{ pagina.label }}
    </a></div>
    <div>
      <KeepAlive>
        <component :is="paginas[paginaAtual].comp" :cidade="cidade" />
      </KeepAlive>
    </div>
  </header>
</template>


<style scoped>
.nav-bar{
  display: flex;
  justify-content: space-evenly;
}

a{
  font-size: 1.5rem;
  padding: 10px;
}
</style>