<template>
                    <h2>Pesquisar vagas</h2>
                    <div class="row">
                        <div class="col">
                            <div class="form-group">
                                <label for="">Titulo da vaga</label>
                                <input type="text" class="form-control" placeholder="Pesquise por palavras chaves, por exemplo PHP">
                                <small class="form-text text-muted">Informe palavras relacionada com o titulo que voce procura</small>
                            </div>
                        </div>
                    </div>
                    <div class="row">
                        <div class="col">
                            <button class="btn btn-outline-dark mt-2">Buscar</button>
                        </div>
                    </div>
</template>

<script>
export default {
    name: 'PesquisarVagas'
}
</script>