<script setup>
import { ref } from 'vue'
const fiche = ref({
  name: 'Kylian Mbappé',
  number: 10,
  position: 'Attaquant',
  club: 'Real Madrid',
  status: 'disponible',
  image:
    'https://upload.wikimedia.org/wikipedia/commons/9/95/Kylian_Mbappe_France_v_Senegal_16_June_2026-391_%28cropped%29.jpg?utm_source=en.wikipedia.org&utm_campaign=index&utm_content=original',
  goals: 100,
  assists: 50,
  games: 200,
})
</script>
<template>
  <div class="card">
    <img :src="fiche.image" :alt="fiche.name" class="avatar" />
    <p class="number">N° {{ fiche.number }}</p>
    <h1>{{ fiche.name }}</h1>
    <p class="position">{{ fiche.position }}</p>
    <p class="club">{{ fiche.club }}</p>
    <div v-if="fiche.status === 'disponible'" class="badge-available">✅ Disponible</div>
    <div v-else-if="fiche.status === 'blessé'" class="badge-injured">🤕 Blessé</div>
    <div v-else class="badge-suspended">🚫 Suspendu</div>
    <div class="stats">
      <div class="stat">
        <div class="stat-value">{{ fiche.goals }}</div>
        <div class="stat-label">Buts</div>
      </div>
      <div class="stat">
        <div class="stat-value">{{ fiche.assists }}</div>
        <div class="stat-label">Passes</div>
      </div>
      <div class="stat">
        <div class="stat-value">{{ fiche.games }}</div>
        <div class="stat-label">Matchs</div>
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
  min-width: 340px;
  box-shadow: 0 8px 32px rgba(0, 0, 0, 0.4);
  text-align: center;
}
.avatar {
  width: 100px;
  height: 100px;
  border-radius: 50%;
  object-fit: cover;
  border: 3px solid #334155;
  margin-bottom: 1rem;
}
.number {
  color: #64748b;
  font-size: 0.85rem;
  margin-bottom: 0.25rem;
}
h1 {
  color: #f1f5f9;
  font-size: 1.4rem;
  margin-bottom: 0.25rem;
}
.position {
  color: #94a3b8;
  font-size: 0.9rem;
  margin-bottom: 0.25rem;
}
.club {
  color: #60a5fa;
  font-size: 0.9rem;
  font-weight: bold;
  margin-bottom: 1rem;
}
.badge-available {
  display: inline-block;
  background: #dcfce7;
  color: #166534;
  border-radius: 999px;
  padding: 0.3rem 1rem;
  font-size: 0.85rem;
  font-weight: bold;
  margin-bottom: 1rem;
}
.badge-injured {
  display: inline-block;
  background: #ffedd5;
  color: #9a3412;
  border-radius: 999px;
  padding: 0.3rem 1rem;
  font-size: 0.85rem;
  font-weight: bold;
  margin-bottom: 1rem;
}
.badge-suspended {
  display: inline-block;
  background: #fee2e2;
  color: #991b1b;
  border-radius: 999px;
  padding: 0.3rem 1rem;
  font-size: 0.85rem;
  font-weight: bold;
  margin-bottom: 1rem;
}
.stats {
  display: flex;
  justify-content: center;
  gap: 1rem;
  border-top: 1px solid #334155;
  padding-top: 1rem;
}
.stat {
  background: #0f172a;
  border-radius: 8px;
  padding: 0.75rem 1rem;
  min-width: 70px;
}
.stat-value {
  font-size: 1.5rem;
  font-weight: bold;
  color: #f1f5f9;
}
.stat-label {
  font-size: 0.7rem;
  color: #64748b;
  text-transform: uppercase;
  letter-spacing: 0.05em;
}
</style>
