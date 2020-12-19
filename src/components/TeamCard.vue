<template>
    <div class="card text-white bg-dark shadow-sm">
        <div class="d-flex justify-content-center p-2 ">
            <img v-bind:src="member.image" alt="Foto del integrante">
        </div>
        <div class="card-body">
            <h5 class="card-title">{{member.nombre}}</h5>
            <p class="card-text"><span>Código: </span>{{member.codigo}}</p>
            <p class="card-text"><span>Descripción: </span>{{member.descripcion}}</p>
            <p class="card-text"><span>Rol: </span>{{member.rol}}</p>
        </div>
    </div>
</template>

<script>
    export default {
        name: "TeamCard",
        props: ['member']
    }
</script>

<style scoped>

</style>
