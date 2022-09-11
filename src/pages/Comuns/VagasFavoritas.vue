<template>
  <div>
    <button
      class="btn btn-outline-success vagasFavoritas"
      type="button"
      data-bs-toggle="offcanvas"
      data-bs-target="#offcanvasRight"
      aria-controls="offcanvasRight"
      style="margin-right: 15px"
    >
      Vagas Favoritas
    </button>

    <div
      class="offcanvas offcanvas-end"
      tabindex="-1"
      id="offcanvasRight"
      aria-labelledby="offcanvasRightLabel"
    >
      <div class="offcanvas-header">
        <h5 id="offcanvasRightLabel">Offcanvas right</h5>
        <button
          type="button"
          class="btn-close text-reset"
          data-bs-dismiss="offcanvas"
          aria-label="Close"
        ></button>
      </div>
      <div class="offcanvas-body">
        <ul class="list-group">
            <li v-for="(vaga, index) in vagas" :key="index" class="list-group-item">{{vaga.titulo}}</li>
        </ul>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "VagasFavoritas",
  data(){
    return{
        vagas:[],
    }
  },
  mounted(){
    this.emitter.on('favoritarVagas', (vaga) => {
        this.vagas.push(vaga)
    })
    this.emitter.on('desfavoritarVagas', (vaga) => {
        let index = this.vagas.indexOf(vaga)
        if(index !== -1){
            this.vagas.splice(index, 1)
        }
    })
  }
};
</script>
<style scoped>

.vagasFavoritas{
    position: fixed;
    top: 10px;
    right: 10px;
    z-index: 1;
}
</style>