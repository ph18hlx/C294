<script setup>
import { ref } from "vue";

const pseudo = ref("ShadowBlade99");
const game = ref("League of Legeends");
const rank = ref("Platine");
const score = ref(4200);
const wins = ref(87);
</script>

<template>
  <div class="card">
    <h1>🎮 {{ pseudo }}</h1>
    <p><strong>Jeu :</strong> {{ game }}</p>
    <p><strong>Rang :</strong> {{ rank }}</p>
    <p><strong>Score :</strong> {{ score }}</p>
    <p><strong>Victoires :</strong> {{ wins }}</p>
  </div>
</template>

<style scoped>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
body {
  font-family: "Arial", sans-serif;
  background: #1a1a2e;
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
}
.card {
  background: #16213e;
  border: 1px solid #0f3460;
  border-radius: 12px;
  padding: 2rem;
  min-width: 350px;
  color: #eee;
}

h1 {
  color: #e94560;
  margin-bottom: 1.5rem;
  font-size: 1.8rem;
}
p {
  margin-bottom: 0.8rem;
  font-size: 1rem;
  color: #a8b2d8;
}
strong {
  color: #ccd6f6;
}
</style>
