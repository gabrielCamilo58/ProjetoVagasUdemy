<template>
  <div class="home" id="app">
    <topo-component @navegar="componet = $event"></topo-component>
   <alerta-comuns v-if="alerta" :titulo="titulo"></alerta-comuns>
    <conteudo-vue :component="componet"></conteudo-vue>
  </div>
</template>

<script>
import TopoComponent from '@/components/layouts/TopoComponent';
import ConteudoVue from '@/components/layouts/Conteudo.vue';
import AlertaComuns from '@/pages/Comuns/AlertaComuns'
export default {
  name: 'HomeView',
  components: {
    TopoComponent,
    ConteudoVue,
    AlertaComuns
  },
  data() {
    return{
      componet: 'home-vue',
      alerta: false,
      titulo: '',
    }
  },
  mounted() {
    this.emitter.on('alerta', (vaga) => {
        this.alerta = true
        this.titulo = vaga.titulo
        setTimeout(() => {
            this.alerta = false
        },4000);
    })
  }
}
</script>
