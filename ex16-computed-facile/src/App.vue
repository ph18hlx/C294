<script setup>
import { ref, computed } from 'vue'

const title = ref('Interstellar')
const director = ref('Christopher Nolan')
const year = ref(2014)

const reviews = ref([
  { name: 'Critique 1', rating: 4 },
  { name: 'Critique 2', rating: 5 },
  { name: 'Critique 3', rating: 4 },
  { name: 'Critique 4', rating: 4 },
])

// Moyenne arrondie à 1 décimale
const averageRating = computed(() => {
  if (reviews.value.length === 0) return 0
  const sum = reviews.value.reduce((total, review) => total + review.rating, 0)
  return Math.round((sum / reviews.value.length) * 10) / 10
})

// Étoiles générées à partir de la moyenne arrondie à l'entier le plus proche
const starsDisplay = computed(() => {
  const fullStars = Math.round(averageRating.value)
  const emptyStars = 5 - fullStars
  return '⭐'.repeat(fullStars) + '☆'.repeat(emptyStars)
})
</script>

<template>
  <div class="card">
    <h1>{{ title }}</h1>
    <p class="meta">{{ director }} · {{ year }}</p>

    <div class="average-box">
      <div class="average-score">{{ averageRating }}</div>
      <div class="average-details">
        <div class="stars">{{ starsDisplay }}</div>
        <div class="reviews-count">{{ reviews.length }} avis</div>
      </div>
    </div>

    <h2>Avis des critiques</h2>
    <div class="review-item" v-for="(review, index) in reviews" :key="index">
      <span class="reviewer-name">{{ review.name }}</span>
      <span class="review-note">⭐ {{ review.rating }}/5</span>
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
.card {
  background: #1f2937;
  border-radius: 16px;
  padding: 2rem;
  min-width: 420px;
  box-shadow: 0 8px 32px rgba(0, 0, 0, 0.4);
}
h1 {
  color: #f9fafb;
  font-size: 1.5rem;
  margin-bottom: 0.25rem;
}
.meta {
  color: #6b7280;
  font-size: 0.85rem;
  margin-bottom: 1.5rem;
}
.average-box {
  background: #111827;
  border-radius: 12px;
  padding: 1rem 1.5rem;
  margin-bottom: 1.5rem;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.average-score {
  font-size: 2.5rem;
  font-weight: bold;
  color: #fbbf24;
}
.average-details {
  text-align: right;
}
.stars {
  font-size: 1.2rem;
  margin-bottom: 0.25rem;
}
.reviews-count {
  color: #6b7280;
  font-size: 0.8rem;
}
h2 {
  color: #d1d5db;
  font-size: 0.9rem;
  text-transform: uppercase;
  letter-spacing: 0.05em;
  margin-bottom: 0.75rem;
}
.review-item {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0.6rem 0;
  border-bottom: 1px solid #374151;
}
.review-item:last-child {
  border-bottom: none;
}
.reviewer-name {
  color: #e5e7eb;
  font-size: 0.9rem;
}
.review-note {
  color: #fbbf24;
  font-size: 0.9rem;
}
</style>
