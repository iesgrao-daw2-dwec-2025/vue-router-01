<script setup>
import { ref } from "vue";
import { useRoute, useRouter } from "vue-router";

const router = useRouter();
const route = useRoute();

const title = ref("");
const description = ref("");
const price = ref(0);
</script>
<template>
  <h1>Crear artículo</h1>
  <div class="article__container">
    <div class="article__title">
      <v-text-field label="Título" v-model="title"></v-text-field>
    </div>
    <div class="article__description">
      <v-textarea label="Descripción" v-model="description"></v-textarea>
    </div>
    <div class="article__price">
      <v-number-input control-variant="split" v-model="price"></v-number-input>
    </div>
  </div>

  <button @click="console.log({ title, description, price })">Crear</button>
  <button @click="$router.push({ name: 'home' })">Volver</button>
</template>

<style scoped>
.article__container {
  margin: 20px;
  max-width: 300px;
}
</style>
