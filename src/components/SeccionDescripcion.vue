<template>
    <div class="description-section">
        <div class="description-section__title">
            <h3>Descripción</h3>
        </div>
        <div v-if="mostrarHijo" class="description-section__principal">
            <div  class="description-section__image">
                <img :src="imagenSeleccionadaHijo.ruta" alt="">
                <p>Autor: <strong>{{imagenSeleccionadaHijo.autor}}</strong></p>
                <button @click="cerrarDescripcion">Cerrar</button>
            </div>
            <div class="description-section__text">
                <h4>{{imagenSeleccionadaHijo.nombre}}</h4>
                <p>{{imagenSeleccionadaHijo.descripcion}}</p>
            </div>
        </div>

    </div>
</template>

<script>
export default {
    name: 'descriptionSection-comp',
    props: {
        imagenSeleccionadaHijo: {
            type: Object,
            required: true,
        },
        mostrarHijo: {
            type: Boolean,
            required: true,
        }
    },
    data: function(){
        return {}
    },
    // computed: {},
    methods: {
        cerrarDescripcion() {
            this.$emit('cerrarDescripcion');
        }
    }
    // watch: {},
    // components: {},
    // mixins: [],
    // filters: {},
    // -- Lifecycle Methods
    // -- End Lifecycle Methods
}
</script>

<style scoped>

    .description-section__title {
        border-bottom: 1px solid black;
        border-left: 1px solid black;
        height: 40px;
        background: lightgray;
        padding-top: 10px;
    }
    .description-section__title h3 {
        text-align: start;
        font-weight: bold;
        padding-left: 10px;
        margin: 0;
    }
    .description-section__principal {
        display: flex;
        height: 100%;
        width: 90%;
        margin: 30px auto;
    }
    .description-section__image {
        width: 60%;
        padding: 10px;
        text-align: start;
    }
    .description-section__image img {
        width: 100%;
    }
    .description-section__image button {
        padding: 5px 25px;
        background-color: cornflowerblue;
        color: white;
        border: 1px solid blue;
        border-radius: 4px;
        margin-top: 40px;
        cursor: pointer;
    }
    .description-section__text {
        width: 40%;
        border: 1px solid black;
        height: 400px;
        overflow: auto;
        text-align: start;
        padding: 0px 10px;
    }
</style>