<template>
    <div class="alert alert-success" role="alert">
        A vaga {{titulo}} foi criada com sucesso!
</div>
</template>
<script>
export default {
    name: 'AlertaComuns',
    props: ['titulo']
}
</script>