<template>
  <div>
    <ComponenteTopo @navegar="componente = $event" />
    <ComponenteConteudo v-if="visibilidade" :conteudo="componente"/>
  </div>
</template>

<script>
import ComponenteConteudo from './components/layouts/ComponenteConteudo.vue'
import ComponenteTopo from './components/layouts/ComponenteTopo.vue'

export default {
  name: 'App',
  data: () => ({
    visibilidade: true,
    componente:'HomePage'
  }),
  components: {
    ComponenteConteudo,
    ComponenteTopo
  }
}
</script>

<style>

</style>
