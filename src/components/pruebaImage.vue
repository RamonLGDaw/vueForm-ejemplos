<template>
    <Vueform>
      <FileElement
        name="image"
        label="Image"
        accept="image/*"
        view="image"
        :rules="[
          'mimetypes:image/jpeg,image/png,image/gif,image/webp,image/svg+xml,image/tiff',
        ]"
        @input="handleFileSelect"
      />
      <button @click="displayImage">Upload</button>
      <div v-if="imageUrl">
        <h3>Uploaded Image:</h3>
        <img :src="imageUrl" alt="Uploaded Image" />
      </div>
    </Vueform>
  </template>
  
  <script>
  import { ref } from 'vue';
  import { Vueform, FileElement } from '@vueform/vueform';
  
  export default {
    components: {
      Vueform,
      FileElement
    },
    setup() {
      const file = ref(null);
      const imageUrl = ref(null);
  
      const handleFileSelect = (uploadedFile) => {
        if (uploadedFile && uploadedFile.length > 0) {
          file.value = uploadedFile[0];
        } else {
          file.value = null;
        }
      };
  
      const displayImage = () => {
        if (file.value) {
          imageUrl.value = URL.createObjectURL(file.value);
        }
      };
  
      return {
        file,
        imageUrl,
        handleFileSelect,
        displayImage
      };
    }
  };
  </script>
  
  <style scoped>
  img {
    max-width: 100%;
    height: auto;
    margin-top: 10px;
  }
  </style>
  