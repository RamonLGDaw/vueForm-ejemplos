<script setup>
import { ref } from 'vue';

let nombreImagenes = ref([]); // Referencia para almacenar los nombres de las imágenes
let imagenesUrl = ref([]); // Referencia para almacenar las URLs de las imágenes

const mostrarImagenes = (name, valor) => {
  const files = valor.data.multiImage;
  nombreImagenes.value = [];
  imagenesUrl.value = [];

  files.forEach(file => {
    nombreImagenes.value.push(file.name);
    const reader = new FileReader();
    reader.readAsDataURL(file);
    reader.onload = () => {
      imagenesUrl.value.push(reader.result);
    };
  });
};
</script>

<template>
  <h2>Multi Image Upload</h2>

  <Vueform :endpoint="mostrarImagenes">
    <MultifileElement
      :upload-temp-endpoint="false"
      name="multiImage"
      label="Multi-image"
      view="image"
      drop
      accept="image/*"
      :file="{
        rules: [
          'mimetypes:image/jpeg,image/png,image/gif,image/webp,image/svg+xml,image/tiff',
        ],
      }"
    />
    <ButtonElement
      name="submit"
      button-label="Submit"
      :submits="true"
    />
  </Vueform>
  
  <!-- Renderizar las imágenes seleccionadas -->
  <div v-if="imagenesUrl.length > 0">
    <h3>Imagenes seleccionadas:</h3>
    <div class="image-grid">
      <div v-for="(nombre, index) in nombreImagenes" :key="index" class="image-item">
        <img :src="imagenesUrl[index]" :alt="`Image ${index + 1}`" class="uploaded-image">
        <p>{{ nombre }}</p>
      </div>
    </div>
  </div>
</template>

<style scoped>
.image-grid {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-wrap: wrap;
  gap: 16px;
}

.image-item {
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 90%; /* Puedes ajustar este valor según sea necesario */
}

.uploaded-image {
  max-width: 100%;
  height: auto;
  border: 1px solid #ddd;
  border-radius: 4px;
  margin-bottom: 8px;
}
</style>