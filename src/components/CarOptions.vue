<template>
    <div>
        <h2>CarOptions API</h2>
        <p>Marca: {{ brand }}</p>
        <p>Modelo: {{ model }}</p>
        <p>Potencia: {{ power }}</p>

        <button @click="UpPower">Aumentar 1</button>
        <button @click="DownPower">Disminuir 1</button>
        <button @click="UpPower50(50)">Aumentar 50</button>
        <button @click="DownPower50(50)">Disminuir 50</button>
    </div>
</template>

<script>
export default {
    //V2
    data() {
        return {
            brand: "Seat",
            model: "Leon",
            power: 50,
        };
    },

    methods: {
        UpPower() {
            // console.log("Aumentando potencia");
            this.power = this.power + 1;
        },
        DownPower() {
            // console.log("Disminuyendo potencia");
            this.power = this.power - 1;
        },
        UpPower50(up50) {
            // console.log("Aumentando potencia");
            this.power = this.power + up50;
        },
        DownPower50(down50) {
            // console.log("Disminuyendo potencia");
            this.power = this.power - down50;
        },
    },
};
</script>

<style lang="scss" scoped></style>
