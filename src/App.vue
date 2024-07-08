<script setup>
import FormBasico from './components/FormBasico.vue'
import Slider from './components/Slider.vue'
import rangeSlider from './components/RangeSlider.vue'
import FormTags from './components/FormTags.vue'
import Toggle from './components/Toggle.vue'
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
</template>

<style scoped>
.contenedor-formulario {
  padding: 10px;
  border: 1px solid #07bf9b;
  border-radius: 5px;
  margin: 10px auto;
  max-width: 600px;
  background-color: rgb(232, 232, 232);
}

h1 {
  text-align: center;
  color: #07bf9b
}

.titulo-degradado {
  font-size: 2em;
  background-image: linear-gradient(to right, #07c6a0, #06977a);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}
</style>
