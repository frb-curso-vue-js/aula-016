<template>
    <div class="usuario-editar">
        <h3>Usuário editar</h3>
        <p><strong>Código:</strong> {{ id }}</p>
        <p><strong>Completo:</strong> {{$route.query.completo ? 'Sim' : 'Não'}}</p>
        <p><strong>Idioma:</strong> {{$route.query.idioma}}</p>
        <button primario @click="confirmou = true">Confirmar</button>
        <hr>
        <div id="rodape">
            <h3>Curso Vue</h3>
        </div>
    </div>
</template>

<script>
export default {
    props: ['id'],
    data() {
        return {
            confirmou: false
        }
    },
    beforeRouteLeave (to, from, next) {
        if (this.confirmou) {
        next()
        } else {
            if (confirm('Tem certeza?')) {
                next()
            } else {
                next(false)
            }
        }
    }
}
</script>

<style>

</style>
