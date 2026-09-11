<script setup>
defineProps({ name: String, game: String, rank: String, score: Number })
</script>
<template>
  <div class="card">
    <h2>{{ name }}</h2>
    <p class="game">{{ game }}</p>
    <p class="rank">🥇{{ rank }}</p>
    <p class="score">{{ score }} pts</p>
  </div>
</template>
<style scoped>
.card {
  background: #1e293b;
  border-radius: 12px;
  padding: 1.25rem 1.5rem;
  min-width: 220px;
  box-shadow: 0 4px 16px rgba(0, 0, 0, 0.3);
  border-top: 3px solid #6366f1;
}
h2 {
  color: #f1f5f9;
  font-size: 1.1rem;
  margin-bottom: 0.5rem;
}
.game {
  color: #6366f1;
  font-size: 0.8rem;
  font-weight: bold;
  margin-bottom: 0.75rem;
}
.rank {
  color: #94a3b8;
  font-size: 0.85rem;
  margin-bottom: 0.25rem;
}
.score {
  color: #fbbf24;
  font-weight: bold;
  font-size: 1rem;
}
</style>
