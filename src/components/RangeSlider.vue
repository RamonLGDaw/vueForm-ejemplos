<script setup>
import {ref} from 'vue'
let valor_A = ref(undefined)
let valor_B = ref(undefined)
const mostrarRangeslider = (datos, formulario) =>{
    console.log(`Que valores hay en el primer valor del RangeSlider?? ${formulario.data.rangeSlider[0]} y en el segundo)) ${formulario.data.rangeSlider[1]}`)
    valor_A.value = formulario.data.rangeSlider[0];
    valor_B.value = formulario.data.rangeSlider[1];
  }

</script>


<template>
  <h2> Range Slider</h2>
    <Vueform :endpoint="mostrarRangeslider">
      <SliderElement
        name="rangeSlider"
        :default="[
          30,
          70,
        ]"
        label="Range slider"
      />
      <ButtonElement
        name="submit"
        button-label="Submit"
        :submits="true"
      />
    </Vueform>
    <p v-if="typeof valor_A == 'number' && typeof valor_B == 'number'">El rango de valores introducidos está entre {{ valor_A }} y {{ valor_B }}</p>
  </template>


<style scoped>
h2, p{
  text-align: center;
}
</style>
