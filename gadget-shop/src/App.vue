<script setup>
import { ref } from 'vue'

const intro = ref({
  titre: 'Vue Gadget Shop',
  description: 'Découvrez les derniers gadgets électroniquesde haute technologie !',
})
const gadgets = ref([
  { name: 'Smartphone XZ', price: 799, image: '../public/phone.jpg', inStock: true },
  { name: 'Laptop Pro', price: 1299, image: '../public/laptop.jpg', inStock: false },
  { name: 'Écouteurs Bluetooth', price: 199, image: '../public/earbuds.jpg', inStock: true },
])
</script>

<template>
  <div>
    <header class="header">
      <h1>{{ intro.titre }}</h1>
      <p>{{ intro.description }}</p>
    </header>
    <main class="main">
      <div class="gadget-container">
        <div v-for="(gadget, index) in gadgets" :key="gadget.id" class="gadget">
          <img :src="gadget.image" :alt="gadget.name" />
          <h2>{{ gadget.name }}</h2>
          <p>{{ gadget.price }}</p>
          <p v-if="gadget.inStock" class="in-stock">✅ En stock</p>
          <p v-else class="out-of-stock">❌ En rupture de stock</p>
        </div>
      </div>
    </main>
  </div>
</template>
<style>
/* ---- BLOC 1 : <style> sans scoped ---- */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
body {
  font-family: 'Arial', sans-serif;
  background: #f5f5f5;
  color: #333;
}
</style>
<style scoped>
/* ---- BLOC 2 : <style scoped> ---- */
.header {
  background: #1a1a2e;
  color: white;
  text-align: center;
  padding: 2rem;
}
.header h1 {
  font-size: 2.5rem;
  margin-bottom: 0.5rem;
}
.header p {
  font-size: 1.1rem;
  color: #a0a0c0;
}
.main {
  max-width: 900px;
  margin: 2rem auto;
  padding: 0 1rem;
}
.gadget {
  background: white;
  border-radius: 12px;
  padding: 1.5rem;
  box-shadow: 0 2px 12px rgba(0, 0, 0, 0.1);
  display: inline-block;
  text-align: center;
  min-width: 220px;
}
.gadget img {
  width: 200px;
  height: 200px;
  object-fit: cover;
  border-radius: 8px;
  display: block;
  margin-bottom: 1rem;
}
.gadget h2 {
  font-size: 1.2rem;
  margin-bottom: 0.5rem;
  color: #1a1a2e;
}
.gadget p {
  color: #666;
  font-size: 0.95rem;
}
.in-stock {
  color: #2e7d32;
  font-weight: bold;
}
.out-of-stock {
  color: #c62828;
  font-weight: bold;
}
.gadget-container {
  display: flex;
  gap: 1.5rem;
  flex-wrap: wrap;
}
</style>
