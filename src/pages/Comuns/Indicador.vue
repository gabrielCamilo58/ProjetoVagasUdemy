<template>
     <div :class="cardColor">
                    <p>{{titulo}}</p>
                    <h2>{{indicador}}</h2>
    </div>
</template>
<script>
export default {
    name: "IndicadorVue",
    props:['titulo', 'indicador', 'bg', 'color'],
    computed:{
        cardColor(){
            return `h-100 p-5 rouded-3 border ${this.bg} ${this.color}`
        }
    }
}
</script>