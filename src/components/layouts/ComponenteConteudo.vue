<template>
  <div>
    <button @click="conteudo = 'HomePage'">Home</button>
    <button @click="conteudo = 'PublicarVaga'">Publicar Vaga</button>
    <!-- renderizar de modo dinâmico os componentes home e publicar-vaga -->
    <!--<home></home>-->
    <!--<publicar-vaga></publicar-vaga>-->
    <keep-alive>
      <component :is="conteudo" />
    </keep-alive>
  </div>
</template>

<script>
import HomePage from '@/components/views/HomePage.vue'
import PublicarVaga from '@/components/views/PublicarVaga.vue'

export default {
  data: () => ({
    conteudo: 'HomePage'
  }),
  components: {
    HomePage,
    PublicarVaga
  }
}
</script>

<style>

</style>