<script setup>
import PlayerCard from './components/PlayerCard.vue'
</script>
<template>
  <div class="players">
    <!-- Utiliser <PlayerCard> 3 fois ici avec des données différentes -->
    <PlayerCard name="Paul" game="cs2" rank="gold" :score="1200"></PlayerCard>
    <PlayerCard name="Jake" game="bo1" rank="platinum" :score="4000"></PlayerCard>
    <PlayerCard name="Toto" game="bo2" rank="diamant" :score="10000"></PlayerCard>
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
.players {
  display: flex;
  gap: 1.5rem;
  flex-wrap: wrap;
  justify-content: center;
}
</style>
