<template>
    <div>
        <h2>CarComposition API</h2>
        <p>Marca: {{ brand }}</p>
        <p>Modelo: {{ model }}</p>
        <p>Potencia: {{ power }}</p>

        <button @click="UpPower">Aumentando potencia</button>
        <button @click="Downpower">Disminuyendo potencia</button>
        <button @click="UpPower50(50)">Aumentar 50</button>
        <button @click="DownPower50(50)">Disminuir 50</button>
    </div>
</template>

<script>
import { ref } from "vue";

export default {
    //V3
    setup() {
        const brand = "audi";
        const model = "A4";
        let power = ref(50);

        const UpPower = () => {
            // console.log("Aumentando potencia");
            power.value = power.value + 1;
        };

        const Downpower = () => {
            // console.log("Disminuyendo potencia");
            power.value = power.value - 1;
        };

        const UpPower50 = (up50) => {
            // console.log("Aumentando potencia");
            power.value = power.value + up50;
        };

        const DownPower50 = (down50) => {
            // console.log("Disminuyendo potencia");
            power.value = power.value - down50;
        };

        return {
            brand,
            model,
            power,
            UpPower,
            Downpower,
            UpPower50,
            DownPower50,
        };
    },
};
</script>

<style lang="scss" scoped></style>
