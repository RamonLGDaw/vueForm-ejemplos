<script setup>
import FormBasico from './components/FormBasico.vue'
import Slider from './components/Slider.vue'
import rangeSlider from './components/RangeSlider.vue'
import FormTags from './components/FormTags.vue'
import Toggle from './components/Toggle.vue'
import DateRange from './components/DateRange.vue'
import DateTime from './components/DateTime.vue'
import imageUpload from './components/imageUpload.vue'
</script>

<template>
  <h1 class="titulo-degradado">Formularios VueForm </h1>
  <div class="contenedor-formulario">
    <FormBasico />
  </div>
  <div class="contenedor-formulario">
    <Slider />
  </div>
  <div class="contenedor-formulario">
    <rangeSlider />
  </div>
  <div class="contenedor-formulario">
    <FormTags />
  </div>
  <div class="contenedor-formulario">
    <Toggle />
  </div>
  <div class="contenedor-formulario">
    <DateRange />
  </div>
  <div class="contenedor-formulario">
    <DateTime />
  </div>
  <div class="contenedor-formulario">
    <imageUpload />
  </div>
</template>

<style scoped>
.contenedor-formulario {
  padding: 10px;
  border: 1px solid rgb(95, 95, 95);
  border-radius: 5px;
  margin: 10px auto;
  max-width: 600px;
  background-color: rgb(232, 232, 232);
}

h1 {
  text-align: center;
}

.titulo-degradado {
  font-size: 2em;
  background-image: linear-gradient(to right, #07c6a0, #06977a);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}
</style>
