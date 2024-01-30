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
                {{ index }} : {{ modelo }}
            </span>
        </p>
        <p>Colores: {{ color }}</p>
        <p>Color Seleccionado: {{ color[0] }}</p>
        <p>Titulo: {{ mensaje.title }}</p>
        <p>Titulo: {{ mensaje.text1 }}</p>
        {{ mensaje.text2 }} - {{ mensaje.text3 }}
        <h4>Ejemplo Lista</h4>
        <ul>
            <li v-for="(modelo, index) in modelos" :key="modelo">
                {{ index }} : {{ modelo }}
            </li>
        </ul>
        <h4>Ejemplo condiciones v-if v-else v-else-if</h4>
        <h4>Coche</h4>
        <p>Marca: {{ brand }}</p>
        <ul>
            <li v-for="(modelo, index) in modelos" :key="modelo">
                {{ index }} : {{ modelo }}
            </li>
        </ul>
        <p>Potencias inferiores a 300 cv</p>
        <ul>
            <!-- la etiqueta template no renderisa -->
            <template v-for="(power, index) in powers" :key="power">
                <!-- {{ index }} : {{ power }} -->
                <li v-if="power < 300">
                    {{ power }}
                </li>
            </template>
        </ul>
        <p>Potencias mayores a 300 cv</p>
        <ul>
            <!-- la etiqueta template no renderisa -->
            <template v-for="(power, index) in powers" :key="power">
                <!-- {{ index }} : {{ power }} -->
                <li v-if="power > 300">
                    {{ power }}
                </li>
            </template>
        </ul>
        <p>Potencias con if-else</p>
        <ul>
            <!-- la etiqueta template no renderisa -->
            <template v-for="(power, index) in powers" :key="power">
                <!-- {{ index }} : {{ power }} -->
                <li v-if="power < 280">Urbana: {{ power }}</li>
                <li v-else-if="power === 280">Hibrido: {{ power }}</li>
                <li v-else>Carrera: {{ power }}</li>
            </template>
        </ul>
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
        const powers = [60, 80, 120, 160, 200, 280, 300, 390, 540, 500];
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
            powers,
            color,
            mensaje,
        };
    },
};
</script>

<style lang="scss" scoped></style>
