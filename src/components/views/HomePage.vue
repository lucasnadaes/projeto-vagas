<template>
  <div class="container py-4">
    <div class="row">
      <div class="col">
        <PesquisarVaga />
      </div>
    </div>

    <div class="row mt-5" v-for="(vaga, index) in vagas" :key="index">
      <div class="col">
        <VagaDescricao :titulo="vaga.titulo" :descricao="vaga.descricao" :salario="vaga.salario" :modalidade="vaga.modalidade" :tipo="vaga.tipo" :publicacao="vaga.publicacao"/>
      </div>
    </div>

    <div class="row mt-5">
      <div class="col-4">
        <IndicadorVaga titulo="Vagas Abertas" indicador="100" bg="bg-dark" color="text-white"/>
      </div>

      <div class="col-4">
        <IndicadorVaga titulo="Profissionais Cadastrados" indicador="250" bg="bg-dark" color="text-white"/>
      </div>

      <div class="col-4">
        <IndicadorVaga titulo="Visitantes Online" :indicador="usuariosOnline" bg="bg-light" color="text-dark"/>
      </div>
    </div>
  </div>
</template>

<script>
import PesquisarVaga from '../comuns/PesquisarVaga.vue'
import IndicadorVaga from '../comuns/IndicadorVaga'
import VagaDescricao from '../comuns/VagaDescricao.vue'

export default {
  name: 'HomePage',
  components: {
    PesquisarVaga,
    IndicadorVaga,
    VagaDescricao
  },
  data: () => ({
    usuariosOnline: 0,
    vagas: []
  }),
  methods: {
    getUsuariosOnline() {
      this.usuariosOnline = Math.floor(Math.random() * 101)
    }
  },
  created() {
    setInterval(this.getUsuariosOnline, 3000)
  },
  activated() {
    this.vagas = JSON.parse(localStorage.getItem('vagas'))
  }
}
</script>

<style>

</style>