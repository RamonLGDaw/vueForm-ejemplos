<script setup>
import { vueform } from '@vueform/vueform';


const mostrarImage = (name, value) => {
   console.log(value.data.image)

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
      :rules="[
        'mimetypes:image/jpeg,image/png,image/gif,image/webp,image/svg+xml,image/tiff',
      ]"
    />
    <ButtonElement
      name="submit"
      button-label="Submit"
      :submits="true"
    />
  </Vueform>
</template>