<script setup>
import { ref } from 'vue'
const pokemon = ref({
  name: 'Pikachu',
  number: 25,
  type: 'Electrik',
  hp: 35,
  image:
    'https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/official-artwork/25.png',
})
</script>

<template>
  <div class="card">
    <div class="pokedex-number">#{{ pokemon.number }}</div>
    <img :src="pokemon.image" :alt="pokemon.image" class="pokemon-image" />
    <h1>{{ pokemon.name }}</h1>
    <div class="type-badge">{{ pokemon.type }}</div>
    <div class="hp">❤ {{ pokemon.hp }} : hp</div>
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
  background: #1a1a2e;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}
.card {
  background: #ffd700;
  border-radius: 16px;
  padding: 1.5rem;
  width: 280px;
  box-shadow: 0 8px 32px rgba(0, 0, 0, 0.4);
  border: 4px solid #b8860b;
  text-align: center;
}
.pokedex-number {
  text-align: right;
  color: #7a6000;
  font-size: 0.85rem;
  font-weight: bold;
  margin-bottom: 0.5rem;
}
.pokemon-image {
  width: 180px;
  height: 180px;
  object-fit: contain;
  background: #fff9c4;
  border-radius: 50%;
  border: 3px solid #b8860b;
  margin-bottom: 1rem;
}
h1 {
  color: #1a1a2e;
  font-size: 1.6rem;
  margin-bottom: 0.5rem;
}
.type-badge {
  display: inline-block;
  background: #f6c90e;
  border: 2px solid #b8860b;
  border-radius: 999px;
  padding: 0.2rem 1rem;
  font-size: 0.85rem;
  font-weight: bold;
  color: #1a1a2e;
  margin-bottom: 1rem;
}
.hp {
  background: #fff9c4;
  border-radius: 8px;
  padding: 0.5rem 1rem;
  font-size: 0.9rem;
  color: #1a1a2e;
  font-weight: bold;
}
</style>
