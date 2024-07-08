<script setup>
import {ref} from 'vue'
let dateTime = ref('')
const mostrarResultados = (datos, formulario) =>{

    console.log(`Que hay dentro de DateTime?? ==> ${formulario.data.dateiime}`) //Devuelve un string con la fecha y la hora
    console.log(formulario.data.datetime)
    dateTime.value = formulario.data.datetime
   

}

</script>

<template>
    <Vueform :endpoint="mostrarResultados">
      <DateElement
        name="datetime"
        label="Datetime"
        :time="true"
      />
      <ButtonElement
        name="submit"
        button-label="Submit"
        :submits="true"
      />
    </Vueform>

    <p v-if="dateTime">La fecha y hora seleccionada es: <strong>{{ dateTime }}</strong></p>
  </template>