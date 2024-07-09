<script setup>
import Text from './components/Text.vue'
import Slider from './components/Slider.vue'
import RangeSlider from './components/RangeSlider.vue'
import Toggle from './components/Toggle.vue'
import DateRange from './components/DateRange.vue'
import DateTime from './components/DateTime.vue'
import ImageUpload from './components/imageUpload.vue'

import { ref } from 'vue'

let listaElementosSeleccionados = ref([])

const mostrarValores = (datos, formulario) => {
  console.log(formulario.data.tags)
  listaElementosSeleccionados.value = formulario.data.tags
}

const componentesFormulario = {
  Text: Text,
  DateTime: DateTime,
  DateRange: DateRange,
  Slider: Slider,
  RangeSlider: RangeSlider,
  Toggle: Toggle,
  ImageUpload: ImageUpload
}
</script>

<template>
  <h1 class="titulo-degradado">Formularios VueForm</h1>
  <div class="contenedor-formulario">
    <h2>Selecciona que formularios quieres probar</h2>
    <Vueform :endpoint="mostrarValores">
      <TagsElement name="tags" 
      :close-on-select="false" 
      :search="true" 
      :items="[
        { value: 'Text', label: 'Text' },
        { value: 'DateTime', label: 'DateTime' },
        { value: 'DateRange', label: 'DateRange' },
        { value: 'Slider', label: 'Slider' },
        { value: 'RangeSlider', label: 'RangeSlider' },
        { value: 'Toggle', label: 'Toggle' },
        { value: 'ImageUpload', label: 'ImageUpload' }
      ]" 
      label="Formularios disponibles:" 
      input-type="search" 
      autocomplete="off" />
      <ButtonElement 
      name="submit" 
      button-label="Submit" 
      :submits="true" />
    </Vueform>

  </div>

  <div v-for="item in listaElementosSeleccionados" :key="item" class="contenedor-formulario">
    <component :is="componentesFormulario[item]" />
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
