<template>
    <div>
        <h2>PasarProps</h2>
        <p>Marca: {{ brand }}</p>
        <p>Modelo: {{ model }}</p>
        <p>Potencia: {{ power }}</p>
        <button @click="upPower">Aumentar...</button>
        <button @click="downPower">Disminuir...</button>
        <h2>Botones Emit</h2>
        <button @click="upPowerEmitFn">Aumentar Emit...</button>
        <button @click="downPowerEmitFn">Disminuir Emit...</button>
    </div>
</template>

<script>
export default {
    //V3
    props: {
        power: {
            type: Number,
            default: 0,
        },

        upPower: Function,

        downPower: Function,
    },

    emits: ["downPowerEmit"],

    setup(props, context) {
        const brand = "audi";
        const model = "A4";

        // console.log(props);

        const upPowerEmitFn = () => {
            context.emit("upPowerEmit");
        };

        const downPowerEmitFn = () => {
            context.emit("downPowerEmit");
        };

        return {
            brand,
            model,
            upPowerEmitFn,
            downPowerEmitFn,
        };
    },
};
</script>

<style lang="scss" scoped></style>
