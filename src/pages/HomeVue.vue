<template>
    <vagas-favoritas></vagas-favoritas>
    <div class="container py-4">
        <div class="row">
            <div class="col">
                <div class="h-100 bg-light p-5 border rouded-3">
                    <pesquisar-vagas></pesquisar-vagas>
                </div>
            </div>
        </div>
        <div class="row mt-2" v-for="(vaga, index) in vagas" :key="index">
            <div class="col" >
                <vaga-vue :vaga="vaga"></vaga-vue>
            </div>
        </div>
        <div class="row mt-5">
            <div class="col-4">
               <indicador-vue :titulo="'Vagas abertas'" :indicador="54" :bg="'bg-dark'" :color="'text-white'"></indicador-vue>
            </div>

            <div class="col-4">
                <indicador-vue :titulo="'Profissionais Cadastrados'" :indicador="105" :bg="'bg-dark'" :color="'text-white'"></indicador-vue>
            </div>

            <div class="col-4">
                <indicador-vue :titulo="'Visitantes Online'" :indicador="25" :bg="'bg-light'" :color="'text-dark'"></indicador-vue>
            </div>
        </div>
    </div>
</template>
<script>
     import PesquisarVagas from '@/pages/Comuns/PesquisarVagas';
     import IndicadorVue from './Comuns/Indicador.vue';
     import VagaVue from '@/pages/Comuns/VagaVue'
     import VagasFavoritas from '@/pages/Comuns/VagasFavoritas'
export default {
name: 'HomeVue',
components:{
    PesquisarVagas,
    IndicadorVue,
    VagaVue,
    VagasFavoritas,
},
data(){
    return{
        vagas: {},
        alerta: false,
    }
},
mounted() {
    this.getVagas();
    this.emitter.on('pesquisa', (vagas) => {
      this.vagas = vagas;
      console.log(this.vagas)
    });
  },
  methods: {
    getVagas() {
      let vagas = JSON.parse(localStorage.getItem("vagas"));
      console.log(vagas);
      if (vagas) {
        this.vagas = vagas;
      }
    },
  },
}
</script>