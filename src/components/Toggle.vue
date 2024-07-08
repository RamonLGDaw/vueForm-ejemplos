<script setup>
import {ref} from 'vue'
let estadoToggle = ref(undefined)
const mostrarResultado = (datos, formulario) =>{
    console.log(`El estado del toggle es: ${formulario.data.toggle}`)
    estadoToggle.value = formulario.data.toggle
}

</script>

<template>
    <h2>Selector Toggle</h2>
    <Vueform :endpoint="mostrarResultado">
      <ToggleElement
        name="toggle"
        text="Toggle"
      />
      <ButtonElement
        name="submit"
        button-label="Submit"
        :submits="true"
      />
    </Vueform>

    <p v-if="estadoToggle != undefined">Estado del toggle: <strong>{{ estadoToggle ? 'TRUE' : 'FALSE' }}</strong></p>
  </template>

  <style scoped>
  h2,p{
    text-align: center;
  }
  strong{
    color: #079276;
    font-size: 1.2rem;
  }
</style>