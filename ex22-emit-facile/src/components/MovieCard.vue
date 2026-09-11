<script setup>
// À compléter
const props = defineProps({
  id: Number,
  title: String,
  genre: String,
  isFavorite: Boolean,
});

const emit = defineEmits(["toggle-favorite"]);

function handleFavorite() {
  emit("toggle-favorite", props.id);
}
</script>
<template>
  <div class="card">
    <h2>{{ props.title }}</h2>
    <p class="genre">{{ props.genre }}</p>
    <button
      :class="['btn-favorite', { active: props.isFavorite }]"
      @click="handleFavorite"
    >
      {{ props.isFavorite ? "❤️Favori" : "🤍Favori" }}
    </button>
  </div>
</template>
<style scoped>
.card {
  background: #1e293b;
  border-radius: 12px;
  padding: 1rem 1.25rem;
  min-width: 200px;
  box-shadow: 0 4px 16px rgba(0, 0, 0, 0.3);
  display: flex;
  flex-direction: column;
  gap: 0.4rem;
}
h2 {
  color: #f1f5f9;
  font-size: 1rem;
  margin: 0;
}
.genre {
  color: #64748b;
  font-size: 0.8rem;
}
.btn-favorite {
  margin-top: 0.5rem;
  background: #1e293b;
  border: 1px solid #334155;
  border-radius: 999px;
  padding: 0.3rem 0.75rem;
  color: #94a3b8;
  font-size: 0.85rem;
  cursor: pointer;
  transition: all 0.2s;
  align-self: flex-start;
}
.btn-favorite.active {
  background: #4c0519;
  border-color: #e11d48;
  color: #fb7185;
}
</style>
