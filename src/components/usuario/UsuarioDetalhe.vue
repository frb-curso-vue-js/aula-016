<template>
    <div class="usuario-detalhe">
        <h3>Usuário detalhe</h3>
        <p><strong>Código:</strong> {{ id }}</p>
        <!-- <router-link tag="button" primario :to="`/usuario/${id}/editar`"> -->
        <router-link tag="button" primario :to="{ name: 'editarUsuario', params: { id }, query: { completo: true, idioma: 'pt' }, hash: '#rodape' }">
            Editar
        </router-link>
    </div> 
</template>

<script>
export default {
    props: ['id'],
    beforeRouteEnter (to, from, next) {
        console.log('dentro do componente -> usuario detalhe')
        /* next(vm => {
            console.log(vm.id)
        }) */
        /* const autenticado = false */
        const autenticado = true
        autenticado ? next() : next('/')
    }
}
</script>

<style>

</style>
