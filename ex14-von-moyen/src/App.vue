<script setup>
import { ref } from 'vue'
const game = ref({
  question: 'Quelle est la capitale de la Suisse ?',
  players: ['Diogo', 'Rayan', 'Ahmed', 'Leo'],
  winner: null,
})
function buzz(playerName) {
  game.value.winner = playerName
}
function reset() {
  game.value.winner = null
}
</script>
<template>
  <div class="container">
    <h1>🎯 Buzzer Quiz</h1>
    <div class="question">❓ {{ game.question }}</div>
    <div class="buzzers">
      <button
        v-for="player in game.players"
        :key="player"
        class="btn-buzzer"
        @click="buzz(player)"
        :disabled="game.winner !== null && game.winner !== player"
        :class="{ winner: game.winner === player }"
      >
        {{ player }}
      </button>
    </div>
    <div v-if="game.winner" class="result">🎉 {{ game.winner }} a buzzé en premier !</div>
    <div v-else class="result-waiting">⏳ En attente d'un buzzer...</div>
    <button @click="reset()" class="btn-reset">🔄 Réinitialiser</button>
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
  min-width: 440px;
  box-shadow: 0 8px 32px rgba(0, 0, 0, 0.4);
  text-align: center;
}
h1 {
  color: #f1f5f9;
  font-size: 1.2rem;
  margin-bottom: 0.5rem;
}
.question {
  color: #60a5fa;
  font-size: 1rem;
  font-style: italic;
  margin-bottom: 2rem;
  padding: 1rem;
  background: #0f172a;
  border-radius: 8px;
  line-height: 1.5;
}
.buzzers {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 1rem;
  margin-bottom: 1.5rem;
}
.btn-buzzer {
  padding: 1.25rem;
  border-radius: 12px;
  border: 2px solid #334155;
  font-size: 1rem;
  font-weight: bold;
  cursor: pointer;
  transition: all 0.2s;
  background: #0f172a;
  color: #94a3b8;
}
.btn-buzzer:hover:not(:disabled) {
  border-color: #60a5fa;
  color: #f1f5f9;
  transform: scale(1.02);
}
.btn-buzzer:disabled {
  opacity: 0.4;
  cursor: not-allowed;
}
.btn-buzzer.winner {
  background: #166534;
  border-color: #4ade80;
  color: #ffffff;
  opacity: 1 !important;
  box-shadow: 0 0 20px rgba(74, 222, 128, 0.3);
}
.result {
  background: #166534;
  border-radius: 12px;
  padding: 1rem;
  margin-bottom: 1.5rem;
  color: #4ade80;
  font-size: 1rem;
  font-weight: bold;
}
.result-waiting {
  background: #0f172a;
  border-radius: 12px;
  padding: 1rem;
  margin-bottom: 1.5rem;
  color: #64748b;
  font-size: 0.95rem;
}
.btn-reset {
  background: #334155;
  border: none;
  border-radius: 8px;
  padding: 0.6rem 1.5rem;
  color: #94a3b8;
  font-size: 0.9rem;
  cursor: pointer;
  transition: all 0.2s;
}
.btn-reset:hover {
  background: #475569;
  color: #f1f5f9;
}
</style>
