<script setup>
import { ref } from "vue"
import BlogPost from "./components/BlogPost.vue";

const posts = ref([
  { title: 'Post 1', id: 1, body: 'Descripción 1' },
  { title: 'Post 2', id: 2, body: 'Descripción 2' },
  { title: 'Post 3', id: 3, body: 'Descripción 3' },
  { title: 'Post 4', id: 4 },
]);

const favorito = ref('');

const cambiarFavorito = (title) => {
  favorito.value = title;
};

</script>

<template>
  <div class="container mt-2">
    <h1>APP</h1>
    <h2>Mi post favorito: {{ favorito }}</h2>

    <BlogPost
      v-for="post in posts"
      :key="post.id"
      :title = "post.title"
      :id = "post.id"
      :body = "post.body"
      @cambiarFavorito="cambiarFavorito"
    ></BlogPost>
  </div>
</template>
<style></style>