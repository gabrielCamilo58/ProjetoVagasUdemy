<template>
  <div
    class="card mt-3"
  >
    <div class="card-header bg-dark text-white">
        <div class="row">
            <div class="col d-flex justify-content-between">
                <div>
                    {{ vaga.titulo }}
                </div>
               <div>
                <div class="form-check form-switch">
                    <input type="checkbox" class="form-check-input" v-model="favoritar">
                    <label class="form-check-label">Favoritar</label>
                </div>
               </div>
            </div>
        </div>
    </div>
    <div class="card-body">
      <p>{{ vaga.description }}</p>
    </div>
    <div class="card-footer">
      <small class="text-muted"
        >Salário: R$ {{ vaga.salario }} | Modalidade: {{ vaga.modalidade }} |
        Tipo: {{ vaga.tipo }}</small
      >
    </div>
  </div>
</template>
<script>
export default {
  name: "VagaVue",
  props:['vaga'],
  data() {
    return {
      favoritar: '',
    };
  },
  watch:{
    favoritar(novoV){
       if(novoV){
        this.emitter.emit('favoritarVagas', this.vaga)
       }else{
        this.emitter.emit('desfavoritarVagas', this.vaga)
       }
    }
  },
};
</script>