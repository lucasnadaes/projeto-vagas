<template>
  <div>
    <VagasFavoritas />
    <ComponenteTopo @navegar="componente = $event" />
    <ComponenteConteudo v-if="visibilidade" :conteudo="componente"/>
  </div>
</template>

<script>
import ComponenteConteudo from './components/layouts/ComponenteConteudo.vue'
import ComponenteTopo from './components/layouts/ComponenteTopo.vue'
import VagasFavoritas from './components/comuns/VagasFavoritas.vue'

export default {
  name: 'App',
  data: () => ({
    visibilidade: true,
    componente:'HomePage'
  }),
  components: {
    ComponenteConteudo,
    ComponenteTopo,
    VagasFavoritas
  }
}
</script>

<style>

</style>
