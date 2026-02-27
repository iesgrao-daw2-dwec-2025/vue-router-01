<script setup>
import { useRoute, useRouter } from "vue-router";

const router = useRouter();
const route = useRoute();

const articles = [
  { title: "Artículo 1", description: "Descripción de artículo 1", price: 10 },
  { title: "Artículo 2", description: "Descripción de artículo 2", price: 10 },
  { title: "Artículo 3", description: "Descripción de artículo 3", price: 10 },
];

const backToHome = () => router.push({ name: "home" });
</script>

<template>
  <v-container>
    <v-col>
      <header>
        <v-container>
          <v-col>
            <h1>Listado de artículos</h1>
          </v-col>
        </v-container>
      </header>
      <main>
        <v-container>
          <v-row>
            <div v-for="article in articles" class="article__container">
              <h1>{{ article.title }}</h1>
              <p>{{ article.description }}</p>
              <p>{{ article.price }}</p>
            </div>
          </v-row>
        </v-container>
      </main>
    </v-col>
  </v-container>
</template>

<style scoped>
.article__container {
  border: 1px solid black;
  margin: 10px;
  background: lightblue;
  max-width: 200px;
}

.item {
  max-width: 50px;
  border: 1px solid red;
}
</style>
