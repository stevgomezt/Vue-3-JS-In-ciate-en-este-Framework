<template>
    <div>
        <h2>Componente car.vue</h2>
        <p>Marca: {{ brand }}</p>
        <p>
            Modelo
            <!-- asigna key unica cuando existen valores repetidos -->
            <span v-for="(modelo, index) in modelos" :key="modelo">
                <!-- asigna key unica cuando los valores son distintos -->
                <!-- <span v-for="modelo in modelos" :key="modelo"> -->
                {{ modelo }}
            </span>
        </p>
        <p>Colores: {{ color }}</p>
        <p>Color Seleccionado: {{ color[0] }}</p>
        <p>Titulo: {{ mensaje.title }}</p>
        <p>Titulo: {{ mensaje.text1 }}</p>
        <p>Titulo: {{ mensaje.text2 }}</p>
        <p>Titulo: {{ mensaje.text3 }}</p>
    </div>
</template>

<script>
export default {
    // V2
    // data() {
    //     return {
    //         brand: "audi",
    //         modelo: "A4",
    //         color: ["azul", "blanco", "rojo"], //Variable tipo array
    //         mensaje: {
    //             title: "Titulo",
    //             text1: "Mensaje1",
    //             text2: "Mensaje2",
    //             text3: "Mensaje3",
    //         }, //Variable de tipo objeto
    //     };
    // },

    //V3
    setup() {
        const brand = "audi";
        const modelos = ["A4", "R8", "Q3"];
        const color = ["azul", "blanco", "rojo"]; //Variable tipo array
        const mensaje = {
            title: "Titulo",
            text1: "Mensaje1",
            text2: "Mensaje2",
            text3: "Mensaje3",
        }; //Variable de tipo objeto

        return {
            brand,
            modelos,
            color,
            mensaje,
        };
    },
};
</script>

<style lang="scss" scoped></style>
