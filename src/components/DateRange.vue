<script setup>
import {ref} from 'vue'
let dateRange = ref([])

const mostrarResultados = (datos, formulario) =>{
    console.log(`Que hay dentro de DateRange: ${formulario.data.dateRange}`)
    dateRange.value = formulario.data.dateRange
}

</script>

<template>
    <h2>Date Range</h2>
    <Vueform :endpoint="mostrarResultados">
      <DatesElement
        name="dateRange"
        label="Date range"
        mode="range"
      />
      <ButtonElement
        name="submit"
        button-label="Submit"
        :submits="true"
      />
    </Vueform>

    <p v-if="dateRange.length > 0">Las fechas seleccionadas van desde el <strong>{{ dateRange[0] }}</strong> hasta el <strong>{{ dateRange[1] }}</strong></p>
  </template>