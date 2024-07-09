<script setup>
import { ref } from 'vue'
let listaElementosSeleccionados = ref([])
const mostrarValores = (datos, formulario) => {
    console.log(formulario.data.tags)
    listaElementosSeleccionados.value = formulario.data.tags
}
</script>
<!-- comentario de prueba -->

<template>
    <h2>Selector múltiples Tags</h2>
    <Vueform :endpoint="mostrarValores">
        <TagsElement name="tags" :close-on-select="false" :search="true" :items="[
            {
                value: 'Python',
                label: 'Python',
            },
            {
                value: 'Java',
                label: 'Java',
            },
            {
                value: 'PHP',
                label: 'PHP',
            },
            {
                value: 'Javascript',
                label: 'Javascript',
            },
            {
                value: 'Go',
                label: 'Go'
            }

        ]" label="Tags" input-type="search" autocomplete="off" />
        <ButtonElement name="submit" button-label="Submit" :submits="true" />
    </Vueform>

    <div class="contenedor-lista" v-if="listaElementosSeleccionados.length > 0">
        <h3>La selección es:</h3>
        <ul>
            <li v-for="item in listaElementosSeleccionados">{{ item }}</li>
        </ul>
    </div>
</template>

<style scoped>
h2{
    text-align: center;
}
.contenedor-lista {
    max-width: 200px;
    margin: auto;
    
}
</style>