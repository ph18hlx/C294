<script setup>
import { ref } from 'vue'
const match = ref({
  team1: 'blue',
  team2: 'red',
  score1: 5,
  score2: 3,
  isLive: true,
  elapsedTime: 60,
  winner: 'blue',
})
</script>
<template>
  <div class="card">
    <div v-if="match.isLive" class="status-live">Match en cours</div>
    <div v-else class="status-ended">⚫ Match terminé</div>
    <div class="match">
      <div class="team">{{ match.team1 }}</div>
      <div class="score">{{ match.score1 }} - {{ match.score2 }}</div>
      <div class="team">{{ match.team2 }}</div>
    </div>
    <p v-show="match.isLive" class="time">⏱ {{ match.elapsedTime }}' écoulées</p>
    <div v-if="!match.isLive" class="result">🏆 Vainqueur : {{ match.winner }}</div>
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
}
.card {
  background: #1e293b;
  border-radius: 16px;
  padding: 2rem;
  min-width: 380px;
  box-shadow: 0 8px 32px rgba(0, 0, 0, 0.4);
  text-align: center;
}
.status-live {
  display: inline-flex;
  align-items: center;
  gap: 0.4rem;
  background: #dcfce7;
  color: #166534;
  border-radius: 999px;
  padding: 0.3rem 1rem;
  font-size: 0.85rem;
  font-weight: bold;
  margin-bottom: 1.5rem;
}
.status-live::before {
  content: '';
  width: 8px;
  height: 8px;
  background: #16a34a;
  border-radius: 50%;
  animation: pulse 1s infinite;
}
.status-ended {
  display: inline-block;
  background: #374151;
  color: #9ca3af;
  border-radius: 999px;
  padding: 0.3rem 1rem;
  font-size: 0.85rem;
  font-weight: bold;
  margin-bottom: 1.5rem;
}
@keyframes pulse {
  0%,
  100% {
    opacity: 1;
  }
  50% {
    opacity: 0.3;
  }
}
.match {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 1.5rem;
  margin-bottom: 1.5rem;
}
.team {
  font-size: 1rem;
  font-weight: bold;
  color: #e2e8f0;
  min-width: 100px;
}
.score {
  font-size: 2.5rem;
  font-weight: bold;
  color: #f1f5f9;
  letter-spacing: 0.1em;
}
.time {
  color: #94a3b8;
  font-size: 0.9rem;
  margin-bottom: 0.5rem;
}
.result {
  background: #1d4ed8;
  color: #bfdbfe;
  border-radius: 8px;
  padding: 0.75rem 1.5rem;
  font-size: 0.95rem;
  font-weight: bold;
  margin-top: 0.5rem;
  display: inline-block;
}
</style>
