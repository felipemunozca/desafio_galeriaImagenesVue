<template>
    <div class="image-section">
        <div class="image-section__title">
            <h2>Galería</h2>
        </div>
        <div class="image-section__individual">
            <div v-for="imagen in detallesImagenHijo" :key="imagen.id">
                <img v-bind:src="imagen.ruta" v-bind:alt="imagen.nombre" @click="mostrarDescripcion(imagen.id)">
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'gallerySection-comp',
    props: {
        detallesImagenHijo: {
            type: Array,
            required: true,
        }
    },
    data: function(){
        return {}
    },
    // computed: {},
    methods: {
        mostrarDescripcion(id) {
            this.$emit('mostrarDescripcion', id);
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
    * {
        box-sizing: border-box;
    }
    .image-section__title {
        height: 50px;
        border-bottom: 1px solid black;
    }
    .image-section__title h2 {
        padding-top: 10px;
        margin: 0;
    }
    .image-section__individual {
        height: 490px;
        overflow: auto;
        padding: 10px;
    }
    .image-section__individual img {
        width: 90%;
        padding: 20px;
    }
</style>