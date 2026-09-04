<script setup>
import { ref } from 'vue'
const author = ref({
  authorName: 'Stephen King',
  authorHandle: '@stephenking',
  authorImage:
    'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcS92YVO4Pz12xn8W3TpBtovCESAbi-6pokhDPujNxpyyHwSStPPE4C28_1e&s=10',
  content: 'It',
  likes: 24,
  isLiked: false,
})

function toggleLike() {
  author.value.likes++
  author.value.isLiked = true
}
</script>
<template>
  <div class="card">
    <div class="author">
      <img :src="author.authorImage" :alt="author.authorName" class="avatar" />
      <div>
        <div class="author-name">{{ author.authorName }}</div>
        <div class="author-handle">{{ author.authorHandle }}</div>
      </div>
    </div>
    <p class="content">{{ author.content }}</p>
    <div class="actions">
      <button @click.once="toggleLike()" class="btn-like">
        {{ author.isLiked ? 'Liké' : '🤍 Liker' }}
      </button>
      <div class="likes-count">
        <span>{{ author.likes }}</span> likes
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
  padding: 2rem;
}
.card {
  background: #1e293b;
  border-radius: 16px;
  padding: 1.5rem;
  min-width: 400px;
  box-shadow: 0 8px 32px rgba(0, 0, 0, 0.4);
}
.author {
  display: flex;
  align-items: center;
  gap: 0.75rem;
  margin-bottom: 1rem;
}
.avatar {
  width: 48px;
  height: 48px;
  border-radius: 50%;
  object-fit: cover;
}
.author-name {
  color: #f1f5f9;
  font-weight: bold;
  font-size: 0.95rem;
}
.author-handle {
  color: #64748b;
  font-size: 0.8rem;
}
.content {
  color: #cbd5e1;
  font-size: 0.95rem;
  line-height: 1.6;
  margin-bottom: 1.25rem;
  padding-bottom: 1.25rem;
  border-bottom: 1px solid #334155;
}
.actions {
  display: flex;
  align-items: center;
  gap: 1rem;
}
.btn-like {
  background: #1e293b;
  border: 1px solid #334155;
  border-radius: 999px;
  padding: 0.4rem 1rem;
  color: #94a3b8;
  font-size: 0.9rem;
  cursor: pointer;
  transition: all 0.2s;
}
.btn-like.liked {
  background: #4c0519;
  border-color: #e11d48;
  color: #fb7185;
}
.likes-count {
  color: #64748b;
  font-size: 0.85rem;
  margin-left: auto;
}
.likes-count span {
  color: #fb7185;
  font-weight: bold;
}
</style>
