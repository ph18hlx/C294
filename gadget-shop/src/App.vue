<script setup>
import { ref } from 'vue'

const intro = ref({
  titre: 'Vue Gadget Shop',
  description: 'Découvrez les derniers gadgets électroniquesde haute technologie !',
})
const gadgets = ref([
  { name: 'Smartphone XZ', price: 799, image: '/phone.jpg', inStock: true },
  { name: 'Laptop Pro', price: 1299, image: '/laptop.jpg', inStock: false },
  { name: 'Écouteurs Bluetooth', price: 199, image: '/earbuds.jpg', inStock: true },
])
const cart = ref([])
function addToCart(gadget) {
  cart.value.push(gadget)
}
function removeFromCart(index) {
  cart.value.splice(index, 1)
}
</script>

<template>
  <div>
    <header class="header">
      <h1>{{ intro.titre }}</h1>
      <p>{{ intro.description }}</p>
    </header>
    <main class="main">
      <div class="cart">
        <h2>🛒 Mon Panier ({{ cart.length }})</h2>
        <ul>
          <li v-for="gadget in cart" :key="gadget">
            {{ gadget.name }} - {{ gadget.price }}
            <button class="remove-btn" @click="removeFromCart(index, 1)">❌</button>
          </li>
        </ul>
        <p v-if="cart.length === 0">Votre panier est vide.</p>
      </div>
      <div class="gadget-container">
        <div v-for="(gadget, index) in gadgets" :key="gadget.id" class="gadget">
          <img :src="gadget.image" :alt="gadget.name" />
          <h2>{{ gadget.name }}</h2>
          <p>{{ gadget.price }}</p>
          <p v-if="gadget.inStock" class="in-stock">✅ En stock</p>
          <p v-else class="out-of-stock">❌ En rupture de stock</p>
          <button class="add-btn" @click="addToCart(gadget)" :disabled="!gadget.inStock">
            Ajouter au panier
          </button>
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
.cart {
  background: white;
  border-radius: 12px;
  padding: 1.5rem;
  box-shadow: 0 2px 12px rgba(0, 0, 0, 0.1);
  margin-bottom: 2rem;
}
.cart h2 {
  color: #1a1a2e;
  font-size: 1.3rem;
  margin-bottom: 1rem;
}
.cart ul {
  list-style: none;
  margin-bottom: 0.5rem;
}
.cart li {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0.5rem 0;
  border-bottom: 1px solid #eee;
  color: #333;
  font-size: 0.95rem;
}
.cart li:last-child {
  border-bottom: none;
}
.cart p {
  color: #999;
  font-style: italic;
  font-size: 0.9rem;
}
.remove-btn {
  background: #fee2e2;
  border: none;
  border-radius: 6px;
  padding: 0.2rem 0.6rem;
  color: #c62828;
  cursor: pointer;
  font-size: 0.85rem;
  transition: background 0.2s;
}
.remove-btn:hover {
  background: #fca5a5;
}
.add-btn {
  margin-top: 0.75rem;
  background: #1a1a2e;
  color: white;
  border: none;
  border-radius: 8px;
  padding: 0.5rem 1rem;
  font-size: 0.9rem;
  cursor: pointer;
  transition: background 0.2s;
}
.add-btn:hover:not(:disabled) {
  background: #2d2d5e;
}
.add-btn:disabled {
  opacity: 0.4;
  cursor: not-allowed;
}
</style>
