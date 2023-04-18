<template>
  <div>
    <ComponenteTopo />
    <ComponenteConteudo />
  </div>
</template>

<script>
import ComponenteConteudo from './components/layouts/ComponenteConteudo.vue'
import ComponenteTopo from './components/layouts/ComponenteTopo.vue'

export default {
  name: 'App',
  components: {
    ComponenteConteudo,
    ComponenteTopo
  }
}
</script>

<style>

</style>
