<script setup>
import FormBasico from './components/FormBasico.vue'
import Slider from './components/Slider.vue'
import rangeSlider from './components/RangeSlider.vue'
import FormTags from './components/FormTags.vue'
</script>

<template>
  <h1 class="titulo-sombra">Formularios Básicos VueForm </h1>
  <div class="contenedor-formulario">
    <FormBasico />
  </div>
  <div class="contenedor-formulario">
    <Slider/>
  </div>
  <div class="contenedor-formulario">
    <rangeSlider/>
  </div>
  <div class="contenedor-formulario">
    <FormTags/>
  </div>
</template>

<style scoped>
.contenedor-formulario {
  padding: 10px;
  border: 1px solid black;
  border-radius: 5px;
  margin: 10px auto;
  max-width: 600px;
  background-color: rgb(232, 232, 232);
}

h1{
  text-align: center;
}

.titulo-sombra {
    font-size: 2em; 
    color: #07bf9b; 
    text-shadow: 0 0 10px rgba(133, 133, 133, 0.5);
}
</style>
