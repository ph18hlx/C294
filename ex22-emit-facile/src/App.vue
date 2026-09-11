<script setup>
// À compléter
import { ref, computed } from "vue";
import MovieCard from "./components/MovieCard.vue";

const films = ref([
  { id: 1, title: "Inception", genre: "Science-Fiction", isFavorite: false },
  { id: 2, title: "Le Roi Lion", genre: "Animation", isFavorite: false },
  { id: 3, title: "Pulp Fiction", genre: "Thriller", isFavorite: false },
  { id: 4, title: "Interstellar", genre: "Science-Fiction", isFavorite: false },
]);
const favorites = computed(() => {
  return films.value.filter((film) => film.isFavorite === true);
});

function onToggleFavorite(id) {
  const film = films.value.find((f) => f.id === id);
  film.isFavorite = !film.isFavorite;
}
</script>
<template>
  <div class="layout">
    <div class="films-grid">
      <!-- Utiliser <MovieCard> avec v-for ici -->
      <MovieCard
        v-for="film in films"
        :key="film.id"
        :id="film.id"
        :title="film.title"
        :genre="film.genre"
        :is-favorite="film.isFavorite"
        @toggle-favorite="onToggleFavorite"
      />
    </div>
    <div class="favorites-section">
      <h2>❤️ Favoris ({{ favorites.length }})</h2>
      <div
        v-for="favorite in favorites"
        :key="favorite.id"
        class="favorite-item"
      >
        {{ favorite.title }}
      </div>
      <p v-if="favorites.length === 0" class="empty">
        Aucun favori pour l'instant.
      </p>
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
  font-family: "Arial", sans-serif;
  background: #0f172a;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: flex-start;
  padding: 2rem;
}
.layout {
  display: flex;
  gap: 2rem;
  align-items: flex-start;
}
.films-grid {
  display: flex;
  flex-direction: column;
  gap: 0.75rem;
}
.favorites-section {
  background: #1e293b;
  border-radius: 16px;
  padding: 1.25rem;
  min-width: 220px;
  box-shadow: 0 8px 32px rgba(0, 0, 0, 0.4);
}
h2 {
  color: #f1f5f9;
  font-size: 1rem;
  margin-bottom: 1rem;
}
.favorite-item {
  color: #fb7185;
  font-size: 0.9rem;
  padding: 0.3rem 0;
  border-bottom: 1px solid #334155;
}
.favorite-item:last-child {
  border-bottom: none;
}
.empty {
  color: #475569;
  font-size: 0.85rem;
  font-style: italic;
}
</style>
