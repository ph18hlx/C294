<script setup>
import { ref } from 'vue'
const game = ref({
  title: 'The Legend of Zelda: Breath of the Wild',
  studio: 'Nintendo',
  year: 2017,
  genre: 'Action-Adventure',
  plateform: 'Nintendo-Switch',
  image:
    'https://upload.wikimedia.org/wikipedia/en/thumb/c/c6/The_Legend_of_Zelda_Breath_of_the_Wild.jpg/250px-The_Legend_of_Zelda_Breath_of_the_Wild.jpg?utm_source=en.wikipedia.org&utm_campaign=parser&utm_content=thumbnail',
  link: 'https://www.fr.fnac.ch/a10337749/The-Legend-of-Zelda-Breath-of-the-Wild-Nintendo-Switch-Jeu-video-Nintendo-Switch',
})
</script>

<template>
  <div class="card">
    <img :src="game.image" :alt="game.title" :title="game.title" class="cover" />
    <div class="content">
      <h1>{{ game.title }}</h1>
      <p class="studio">{{ game.studio }}</p>
      <div class="tags">
        <span class="tag">🎮 {{ game.platform }}</span>
        <span class="tag">🗂 {{ game.genre }}</span>
        <span class="tag">📅 {{ game.year }}</span>
      </div>
      <a :href="game.link" :title="game.title" class="link" target="_blank"
        >🌐 Voir le site officiel
      </a>
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
  background: #0d1117;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}
.card {
  background: #161b22;
  border-radius: 16px;
  width: 320px;
  box-shadow: 0 8px 32px rgba(0, 0, 0, 0.6);
  overflow: hidden;
  border: 1px solid #30363d;
}
.cover {
  width: 100%;
  height: 200px;
  object-fit: cover;
  display: block;
}
.content {
  padding: 1.25rem;
}
h1 {
  color: #e6edf3;
  font-size: 1.3rem;
  margin-bottom: 0.25rem;
}
.studio {
  color: #58a6ff;
  font-size: 0.85rem;
  margin-bottom: 1rem;
}
.tags {
  display: flex;
  gap: 0.5rem;
  flex-wrap: wrap;
  margin-bottom: 1rem;
}
.tag {
  background: #21262d;
  border: 1px solid #30363d;
  border-radius: 999px;
  padding: 0.2rem 0.75rem;
  font-size: 0.75rem;
  color: #8b949e;
}
.link {
  display: block;
  text-align: center;
  background: #238636;
  color: #ffffff;
  text-decoration: none;
  border-radius: 8px;
  padding: 0.6rem;
  font-size: 0.9rem;
  font-weight: bold;
  transition: background 0.2s;
}
.link:hover {
  background: #2ea043;
}
</style>
