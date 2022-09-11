<template>
<div style="margin-bottom:58px">
  <nav class="navbar navbar-expand-lg navbar-light bg-light" style="position:fixed; min-width: 100vw; top: 0; z-index: 1;">
  <div class="container-fluid">
    <a class="navbar-brand" href="#">Vagas</a>
    <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navbarSupportedContent">
      <ul class="navbar-nav me-auto mb-2 mb-lg-0">
        <li class="nav-item">
          <a class="nav-link" aria-current="page" @click.prevent="navegarPara('home-vue')" style="cursor: pointer;">Home</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" @click.prevent="navegarPara('pagina-vaga-vue')"  style="cursor: pointer;">Publicar vaga</a>
        </li>
      </ul>
    </div>
  </div>
</nav>
</div>
</template>
<script>
export default {
    methods: {
      navegarPara(p) {
        this.$emit('navegar', p);
      }
    }
}
</script>