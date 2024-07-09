<script setup>
import {ref} from 'vue'
let nombre = ref('')
const  mostrarResultados = (datos, formulario) =>{
    console.log(`Que hay en el formulario básico?? ==> ${formulario.data.nombre}`)
    nombre.value = formulario.data.nombre
}



</script>

<template>
  <h2>Texto</h2>
  <div class="container">
    <Vueform :endpoint="mostrarResultados">
      <TextElement name="nombre" label="Texto"  />
      <ButtonElement
      name="submit"
      button-label="Submit"
      :submits="true"
    />
    </Vueform>
  </div>

  <div class="container" v-if="nombre !== '' && typeof nombre === 'string'">
    <p>El texto introducido es: <strong>{{ nombre }}</strong></p>
  </div>

</template>

<style scoped>


</style>
