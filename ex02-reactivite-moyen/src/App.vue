<script setup>
import { ref } from 'vue'
const athlete = ref({
  name: 'Cristiano Ronaldo',
  sport: 'football',
  country: 'Portugal',
  age: 41,
  goldMedals: 45,
  silverMedals: 40,
  bronzeMedals: 35,
  status: 'GOAT',
})
</script>

<template>
  <div class="card">
    <div class="card-header">
      <h1>{{ athlete.name }}</h1>
      <p class="sport">{{ athlete.sport }}</p>
    </div>
    <div class="info-grid">
      <div class="info-item">
        <div class="info-label">Pays</div>
        <div class="info-value">{{ athlete.country }}</div>
      </div>
      <div class="info-item">
        <div class="info-label">Âge</div>
        <div class="info-value">{{ athlete.age }}</div>
      </div>
    </div>
    <div class="medals">
      <div class="medal">
        <div class="medal-count">{{ athlete.goldMedals }}</div>
        <div class="medal-label">🥇 Or</div>
      </div>
      <div class="medal">
        <div class="medal-count">{{ athlete.silverMedals }}</div>
        <div class="medal-label">🥈 Argent</div>
      </div>
      <div class="medal">
        <div class="medal-count">{{ athlete.bronzeMedals }}</div>
        <div class="medal-label">🥉 Bronze</div>
      </div>
    </div>
    <div class="status">{{ athlete.status }}</div>
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
  padding: 2rem 2.5rem;
  min-width: 380px;
  box-shadow: 0 8px 32px rgba(0, 0, 0, 0.4);
  border-top: 4px solid #3b82f6;
}
.card-header {
  margin-bottom: 1.5rem;
  padding-bottom: 1rem;
  border-bottom: 1px solid #334155;
}
h1 {
  color: #f1f5f9;
  font-size: 1.6rem;
  margin-bottom: 0.25rem;
}
.sport {
  color: #3b82f6;
  font-size: 1rem;
  font-weight: bold;
}
.info-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 1rem;
  margin-bottom: 1.5rem;
}
.info-item {
  background: #0f172a;
  border-radius: 8px;
  padding: 0.75rem 1rem;
}
.info-label {
  color: #64748b;
  font-size: 0.75rem;
  text-transform: uppercase;
  letter-spacing: 0.05em;
  margin-bottom: 0.25rem;
}
.info-value {
  color: #e2e8f0;
  font-size: 1rem;
  font-weight: bold;
}
.medals {
  display: flex;
  gap: 1rem;
  justify-content: center;
  margin-bottom: 1.5rem;
}
.medal {
  text-align: center;
  background: #0f172a;
  border-radius: 8px;
  padding: 0.75rem 1.25rem;
}
.medal-count {
  font-size: 1.5rem;
  font-weight: bold;
  color: #f1f5f9;
}
.medal-label {
  font-size: 0.75rem;
  color: #64748b;
}
.status {
  text-align: center;
  padding: 0.5rem 1rem;
  border-radius: 999px;
  font-size: 0.875rem;
  font-weight: bold;
  background: #166534;
  color: #86efac;
  display: inline-block;
}
</style>
