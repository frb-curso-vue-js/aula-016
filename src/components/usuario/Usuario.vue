<template>
    <div class="usuario">
        <h2>Usuários</h2>
        <hr>
        <router-view />
        <hr>
        <button sucesso @click="irParaInicio">Voltar</button>
    </div>
</template>

<script>
export default {
/*     data() {
        return {
            id: this.$route.params.id
        }
    }, */
    methods: {
        irParaInicio() {
            if (this.$route.path === '/usuario') {
                this.$router.push({name: 'Inicio'})
            } else {
                this.$router.push('/usuario')
            }
        }
    }
    /* watch: {
        $route(to, from) {
            this.id = to.params.id
        }
    } */
}
</script>

<style>

</style>
