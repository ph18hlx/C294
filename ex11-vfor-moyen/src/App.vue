<script setup>
import { ref } from 'vue'
const players = ref([
  { id: 1, name: 'Alexandre Dubois', country: 'France', score: 2450, wins: 32 },
  { id: 2, name: 'Lena Fischer', country: 'Allemagne', score: 2310, wins: 28 },
  { id: 3, name: 'Marco Rossi', country: 'Italie', score: 2180, wins: 25 },
  { id: 4, name: 'Sofia Alvarez', country: 'Espagne', score: 2600, wins: 40 },
  { id: 5, name: "Liam O'Connor", country: 'Irlande', score: 1980, wins: 19 },
])
</script>
<template>
  <div class="container">
    <h1>🏆 Classement des joueurs</h1>
    <div
      v-for="(player, index) in players"
      :key="player.id"
      class="player-row"
      :class="{ first: index === 0 }"
    >
      <div class="position">{{ index + 1 }}</div>
      <div v-if="index === 0" class="medal">🥇</div>
      <div v-else-if="index === 1" class="medal">🥈</div>
      <div v-else="index === 2" class="medal">🥉</div>
      <div class="player-name">{{ player.name }}</div>
      <div class="player-country">{{ player.country }}</div>
      <div class="player-wins">🏆 {{ player.wins }} Victoires</div>
      <div class="player-score">{{ player.score }} pts</div>
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
  background: #0f172a;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 2rem;
}
.container {
  background: #1e293b;
  border-radius: 16px;
  padding: 2rem;
  min-width: 500px;
  box-shadow: 0 8px 32px rgba(0, 0, 0, 0.4);
}
h1 {
  color: #f1f5f9;
  font-size: 1.4rem;
  margin-bottom: 1.5rem;
  padding-bottom: 0.75rem;
  border-bottom: 2px solid #334155;
  text-align: center;
}
.player-row {
  display: flex;
  align-items: center;
  gap: 1rem;
  padding: 0.75rem 1rem;
  border-radius: 10px;
  margin-bottom: 0.5rem;
  background: #0f172a;
  transition: transform 0.1s;
}
.player-row:hover {
  transform: translateX(4px);
}
.player-row.first {
  background: #713f12;
  box-shadow: 0 0 16px rgba(251, 191, 36, 0.2);
}
.position {
  color: #64748b;
  font-size: 0.9rem;
  font-weight: bold;
  min-width: 24px;
  text-align: center;
}
.medal {
  font-size: 1.2rem;
  min-width: 24px;
  text-align: center;
}
.player-name {
  flex: 1;
  color: #f1f5f9;
  font-weight: bold;
  font-size: 0.95rem;
}
.player-country {
  color: #94a3b8;
  font-size: 0.85rem;
}
.player-wins {
  color: #4ade80;
  font-size: 0.85rem;
  min-width: 70px;
  text-align: right;
}
.player-score {
  color: #fbbf24;
  font-weight: bold;
  font-size: 1rem;
  min-width: 80px;
  text-align: right;
}
</style>
