<template>
    <div class="container py-4">
        <div class="row">
            <dic class="col">
                <h4>Apresente a sua vaga para milhares de profissionais e de graça</h4>
            </dic>
        </div>
        <div class="row mt-3">
            <div class="col">
                <label for="" class="form-label">Titulo da vaga</label>
                <input type="text" class="form-control" v-model="vaga.titulo">
                <div class="form-text">Por exemplo: Programador JavaSscript e VueJs.</div>
            </div>
        </div>
        <div class="row mt-3">
            <div class="col">
                <label for="" class="form-label">Descrição</label>
                <textarea cols="30" rows="10" class="form-control" v-model="vaga.description"></textarea>
                <div class="form-text">Informe os detalhes da vaga.</div>
            </div>
        </div>
        <div class="row mt-3">
            <div class="col">
                <label for="" class="form-label">Salário</label>
                <input type="number" class="form-control" v-model="vaga.salario">
                <div class="form-text">Informe o Salario</div>
            </div>
            <div class="col">
                <label for="" class="form-label">Modalidade</label>
                <select name="" id="" class="form-select" v-model="vaga.modalidade">
                    <option value="0" selected disabled>--Selecione</option>
                    <option value="Home Office">Home Office</option>
                    <option value="Presencial">Presencial</option>
                </select>
                <div class="form-text">Informe onde as atividades serão realizadas</div>
            </div>
            <div class="col">
                <label for="" class="form-label">Tipo</label>
                <select name="" id="" class="form-select" v-model="vaga.tipo">
                    <option value="0" selected disabled>--Selecione</option>
                    <option value="CLT">CLT</option>
                    <option value="PJ">PJ</option>
                </select>
                <div class="form-text">Informe o tipo de contratação</div>
            </div>
        </div>
        <div class="row">
            <div class="col">
                <button class="btn btn-primary" @click.prevent="salvar">Cadastrar</button>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    name: 'PaginaVaga',
    data() {
        return{
            vaga: {}
        }
    },
    methods: {
    salvar(){
        let vagas = JSON.parse(localStorage.getItem('vagas'));
        if(!vagas) vagas = [];
        vagas.push(this.vaga);
        localStorage.setItem('vagas', JSON.stringify(vagas));
        console.log(localStorage.getItem('vagas'))
        this.emitter.emit('alerta', this.vaga)
        this.vaga = {};
    }
}
}
</script>