<script setup>
import { ref } from 'vue'
const movie = ref({
  title: 'Inception',
  director: 'Christopher Nolan',
  year: 2010,
  genre: 'Science-Fiction',
  duration: 148,
  rating: 4,
  synopsis: 'Film sur les rêves lucides',
})
</script>

<template></template>

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
}
.card {
  background: #1f2937;
  border-radius: 16px;
  padding: 2rem 2.5rem;
  max-width: 440px;
  width: 100%;
  box-shadow: 0 8px 32px rgba(0, 0, 0, 0.5);
  border-left: 4px solid #f59e0b;
}
.genre-badge {
  display: inline-block;
  background: #f59e0b22;
  color: #f59e0b;
  border: 1px solid #f59e0b;
  border-radius: 999px;
  padding: 0.2rem 0.75rem;
  font-size: 0.75rem;
  font-weight: bold;
  margin-bottom: 0.75rem;
  text-transform: uppercase;
  letter-spacing: 0.05em;
}
h1 {
  color: #f9fafb;
  font-size: 1.8rem;
  margin-bottom: 0.25rem;
}
.director {
  color: #9ca3af;
  font-size: 0.9rem;
  margin-bottom: 1.25rem;
}
.meta {
  display: flex;
  gap: 1.5rem;
  margin-bottom: 1.25rem;
}
.meta-item {
  text-align: center;
}
.meta-label {
  color: #6b7280;
  font-size: 0.7rem;
  text-transform: uppercase;
  letter-spacing: 0.05em;
}
.meta-value {
  color: #e5e7eb;
  font-size: 1rem;
  font-weight: bold;
}
.stars {
  font-size: 1.5rem;
  margin-bottom: 1.25rem;
  letter-spacing: 0.1em;
}
.synopsis {
  color: #9ca3af;
  font-size: 0.9rem;
  line-height: 1.6;
  border-top: 1px solid #374151;
  padding-top: 1rem;
}
</style>
