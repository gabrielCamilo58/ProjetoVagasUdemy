<template>
    <div>
    <component :is='component'></component>
    </div>
</template>
<script>
    import PaginaVagaVue from '@/pages/PaginaVaga.vue';
    import HomeVue from '@/pages/HomeVue.vue';
export default {
name: 'ConteudoVue',
props :['component'],
components:{
    PaginaVagaVue,
    HomeVue,
}, 
data(){
    return{
        componentSelect: 'home-vue',
    }
}
}
</script>