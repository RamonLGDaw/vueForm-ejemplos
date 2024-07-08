<script setup>
import {ref} from 'vue'
let valor = ref(undefined)
const mostrarSlider = (datos, formulario) => {
    console.log(`Que valor hay en el slider?? ===> ${formulario.data.slider}`)
    valor.value = formulario.data.slider
}

</script>

<template>
    <h2>Slider</h2>
    <Vueform :endpoint="mostrarSlider">
        <SliderElement name="slider" label="Slider" :default="30" />

        <ButtonElement name="submit" button-label="Submit" :submits="true" />
    </Vueform>
    <p v-if="typeof valor == 'number'">El valor seleccionado es: {{ valor }}</p>
</template>

<style scoped>
h2, p{
    text-align: center;
}
</style>