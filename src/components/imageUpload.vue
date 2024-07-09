<script setup>
import { vueform } from '@vueform/vueform';


const mostrarImage = (name, valor) => {
   console.log(valor.data.image)

}
</script>

<template>
    <h2>Image Upload</h2>

   
  <Vueform :endpoint="mostrarImage">
    <FileElement
      name="image"
      label="Image"
      accept="image/*"
      view="image"
      :auto="false"
      :rules="[
        'mimetypes:image/jpeg,image/png,image/gif,image/webp,image/svg+xml,image/tiff',
      ]"
    />
    
  </Vueform>
</template>