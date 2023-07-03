<template>
    <div class="principal-container">
        <div class="image-container">
            <nueva-seccion-galeria 
            :detallesImagenHijo="detallesImagen" 
            @mostrarDescripcion="mostrarDescripcionPadre"/>
        </div>
        <div class="description-container">
            <nueva-seccion-descripcion 
            :imagenSeleccionadaHijo="imagenSeleccionada" 
            :mostrarHijo="mostrar"
            @cerrarDescripcion="cerrarDescripcionPadre" />
        </div>
    </div>
</template>

<script>

/**
 * Se importan los archivos para cargar los componentes de la vista.
 */
import SeccionGaleria from '@/components/SeccionGaleria.vue';
import SeccionDescripcion from '@/components/SeccionDescripcion.vue';

export default {
    name: 'gallery-comp',
    // props: {},
    data: function(){
        return {
            detallesImagen: [
                {
                    id: "1",
                    nombre: "Parque Tantauco",
                    autor: "Agustina Muñoz",
                    descripcion: "Este parque conserva uno de los bosques más antiguos y salvajes de Chile. De árboles milenarios y turberas que datan de la última glaciación, alberga a especies endémicas y en peligro de extinción como el zorro de Darwin, el gato de Geoffroy y el pudú.​",
                    ruta: "https://picsum.photos/id/704/600/400",
                },
                {
                    id: "2",
                    nombre: "Parque Nacional Torres del Paine",
                    autor: "Luis Gonzalez",
                    descripcion: "Es conocido por sus altas montañas, los témpanos de azul brillante que se aferran a los glaciares y las pampas doradas (praderas) que albergan fauna poco común, como los guanacos. Algunos de los sitios más icónicos son las 3 torres de granito que le dan nombre al parque y las cimas con forma de cuernos llamadas Cuernos del Paine.",
                    ruta: "https://picsum.photos/id/684/600/400",
                },
                {
                    id: "3",
                    nombre: "Carretera Austral",
                    autor: "Camila Gonzalez",
                    descripcion: "Es una carretera chilena que se encuentra en la zona sur-austral de Chile. Para el año 2014 el recorrido era de 1240 kilómetros y unía a Puerto Montt con Villa O'Higgins, ​aunque el proyecto es que en el futuro llegue hasta Puerto Williams.​",
                    ruta: "https://picsum.photos/id/688/600/400",
                },
                {
                    id: "4",
                    nombre: "Viña del Mar",
                    autor: "Cristobal Muñoz",
                    descripcion: "Es una ciudad turística costera al noroeste de Santiago de Chile. Es conocida por sus jardines, playas y altos edificios. En el Parque Quinta Vergara se encuentra el Anfiteatro Quinta Vergara, el Palacio Vergara de comienzos del siglo XX y el Museo Artequin, que exhibe copias de importantes obras de arte. El Museo de Arqueología e Historia Francisco Fonck cuenta con esculturas moái de piedra de la Isla de Pascua y cabezas reducidas.​",
                    ruta: "https://picsum.photos/id/689/600/400",
                },
                {
                    id: "5",
                    nombre: "Santiago de Chile",
                    autor: "Alberto Muñoz",
                    descripcion: "La capital y la ciudad más grande de Chile, se ubica en un valle rodeado de cimas nevadas de los Andes y la Cordillera de la Costa chilena. La Plaza de Armas, el gran núcleo del centro colonial antiguo de la ciudad, tiene 2 monumentos neoclásicos: el Palacio de la Real Audiencia de 1808, donde está el Museo Histórico Nacional, y la Catedral Metropolitana del siglo XVIII. La Chascona es la casa transformada en museo del poeta Pablo Neruda.​",
                    ruta: "https://picsum.photos/id/690/600/400",
                },
                {
                    id: "6",
                    nombre: "Lluvia de estrellas",
                    autor: "Mirta Caceres",
                    descripcion: "Fenómeno que se produce cuando minúsculas partículas de polvo, procedentes de algún cometa, entran en la atmósfera terrestre a gran velocidad y se desintegran por fricción, lo que produce el rastro luminoso que llamamos meteoro o estrella fugaz.",
                    ruta: "https://picsum.photos/id/683/600/400",
                },
            ],
            imagenSeleccionada: {},
            mostrar: false,
        }
    },
    // computed: {},
    methods: {
        mostrarDescripcionPadre(id) {
            const imagenEncontrada = this.detallesImagen.find(imagen => imagen.id == id);
            this.imagenSeleccionada = imagenEncontrada;
            this.mostrar = true;
        },
        cerrarDescripcionPadre() {
            this.mostrar = false;
        },
    },
    // watch: {},
    components: {
        'nueva-seccion-galeria': SeccionGaleria,
        'nueva-seccion-descripcion': SeccionDescripcion,
    },
    // mixins: [],
    // filters: {},
    // -- Lifecycle Methods
    // -- End Lifecycle Methods
}
</script>

<style scoped>
    .principal-container {
        border: 1px solid black;
        width: 80%;
        margin: 0 auto;
        display: flex;
        max-width: 1000px;
    }
    .image-container {
        width: 40%;
    }
    .description-container {
        width: 60%;
    }
</style>