<script setup>
import { ref } from 'vue'

const intro = ref({
  titre: 'Vue Gadget Shop',
  description: 'Découvrez les derniers gadgets électroniquesde haute technologie !',
})
</script>

<template>
  <div>
    <header class="header">
      <h1>{{ intro.titre }}</h1>
      <p>{{ intro.description }}</p>
    </header>
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
</style>
