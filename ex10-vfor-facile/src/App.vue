<script setup>
// À compléter
import { ref } from 'vue'
const films = ref([
  { id: 1, title: 'Inception', year: 2010, genre: 'Science-fiction', rating: 5 },
  {
    id: 2,
    title: "Le Fabuleux Destin d'Amélie Poulain",
    year: 2001,
    genre: 'Comédie romantique',
    rating: 5,
  },
  { id: 3, title: 'Interstellar', year: 2014, genre: 'Science-fiction', rating: 4 },
  { id: 4, title: 'Parasite', year: 2019, genre: 'Thriller', rating: 3 },
  { id: 5, title: 'La Haine', year: 1995, genre: 'Drame', rating: 4 },
])
</script>
<template>
  <div class="container">
    <h1>🎬 Mes films favoris</h1>
    <div v-for="film in films" :key="film.id" class="film-item">
      <div class="film-info">
        <div class="film-title">{{ film.title }}</div>
        <div class="film-meta">{{ film.year }} · {{ film.genre }}</div>
      </div>
      <div class="film-right">
        <div class="stars">{{ '⭐'.repeat(film.rating) }}{{ '☆'.repeat(5 - film.rating) }}</div>
      </div>
    </div>
  </div>
</template>
<style scoped>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
body {
  font-family: 'Arial', sans-serif;
  background: #111827;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 2rem;
}
.container {
  background: #1f2937;
  border-radius: 16px;
  padding: 2rem;
  min-width: 400px;
  box-shadow: 0 8px 32px rgba(0, 0, 0, 0.4);
}
h1 {
  color: #f9fafb;
  font-size: 1.4rem;
  margin-bottom: 1.5rem;
  padding-bottom: 0.75rem;
  border-bottom: 2px solid #374151;
}
.film-item {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0.75rem 0;
  border-bottom: 1px solid #374151;
}
.film-item:last-child {
  border-bottom: none;
}
.film-info {
  flex: 1;
}
.film-title {
  color: #f3f4f6;
  font-size: 1rem;
  font-weight: bold;
  margin-bottom: 0.2rem;
}
.film-meta {
  color: #6b7280;
  font-size: 0.8rem;
}
.film-right {
  text-align: right;
}
.stars {
  font-size: 0.9rem;
}
</style>
