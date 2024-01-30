<template>
    <div>
        <h1>Vuejs App</h1>
        <hr />
        <Car
            :power="power"
            :upPower="upPower"
            :downPower="downPower"
            @upPowerEmit="upPowerEmit"
            @downPowerEmit="downPowerEmit"
        />
        <!-- <Car /> -->
        <hr />
        <CarInfo />
        <hr />
        <CarOptions />
        <hr />
        <CarComposition />
    </div>
</template>

<script>
import { ref } from "vue";
import Car from "./components/Car.vue";
import CarInfo from "./components/CarInfo.vue";
import CarOptions from "./components/CarOptions.vue";
import CarComposition from "./components/CarComposition.vue";

export default {
    components: {
        Car,
        CarInfo,
        CarOptions,
        CarComposition,
    },

    setup() {
        let power = ref(30);

        const upPower = () => {
            power.value++;
        };

        const downPower = () => {
            power.value--;
        };

        const upPowerEmit = () => {
            power.value++;
        };

        const downPowerEmit = () => {
            power.value--;
        };

        return {
            power,
            upPower,
            downPower,
            upPowerEmit,
            downPowerEmit,
        };
    },
};
</script>

<style lang="scss" scoped></style>
