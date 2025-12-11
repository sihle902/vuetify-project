<template>
  <div :class="['page-container', { 'dark-mode': isDarkMode }]">

    <!-- AfriGIS Banner -->
    <div class="afrigis-banner">
      AfriGIS
    </div>

    <!-- Mode Toggle Button -->
    

    <!-- Header -->
    <h1>Employee profile:</h1>

   <button id="mode-toggle" @click="toggleMode">
  <span v-if="isDarkMode">🌙</span>
<span v-else>☀️</span>          <!-- Sun icon for light mode -->
</button> <!-- Navigation Menu -->
    <nav class="menu">
  <router-link to="/">Home</router-link>
  <router-link to="/about">About</router-link>
  <router-link to="/contact">Contact</router-link>
  <router-link to="/projects">Projects</router-link>
</nav>



    <!-- Centered Image -->
    <div class="center-screen">
      <img src="/IMG225.JPEG" alt="IM225" />
    </div>
    <footer class="footer">
  <h3>AfriGIS </h3>
  <p>446 Rigel Avenue South, Erasmusrand, Pretoria, South Africa</p>
  <p>Postal: P.O. Box 28274, Sunnyside, Pretoria, 0132</p>
</footer>

  </div>
  
</template>

<script setup>
import { ref } from 'vue'

// Reactive state to track dark mode
const isDarkMode = ref(false)

// Toggle function
const toggleMode = () => {
  isDarkMode.value = !isDarkMode.value
}
</script>

<style scoped>
  .footer {
  padding: 20px;
  background: #70b6dc;
}

.footer-input {
  width: 100%;              /* full width */
  padding: 12px;
  margin-top: 15px;
  border: 1px solid #ccc;
  border-radius: 6px;
  font-size: 16px;
  box-sizing: border-box;   /* prevents overflow */
}
/* Page container */
.page-container {
  background-color: rgb(232, 238, 240);
  font-family: Verdana;
  text-align: center;
  min-height: 100vh;
  transition: background-color 0.3s, color 0.3s;
}

/* Dark mode styling */
.page-container.dark-mode {
  background-color: #1e1e2f;
  color: #e0e0e0;
}

/* Header */
h1 {
  font-size: 24px;
  font-weight: bold;
  color: rgb(2, 52, 69);
  border-radius: 8px;
  margin-bottom: 20px;
  transition: color 0.3s;
}

.page-container.dark-mode h1 {
  color: #f0f0f0;
}

/* AfriGIS Banner */
.afrigis-banner {
  position: absolute;
  top: 20px;
  left: 0;
  background-color: rgb(6, 76, 96);
  color: white;
  padding: 15px 25px;
  border-radius: 15px;
  display: inline-block;
  font-weight: bold;
  font-size: 22px;
  white-space: nowrap;
  animation: move-banner 15s linear infinite alternate;
  transition: background-color 0.3s;
}

.page-container.dark-mode .afrigis-banner {
  background-color: #0a2a3e;
  color: #fff;
}

@keyframes move-banner {
  0% { left: 0; }
  100% { left: calc(100% - 120px); }
}

/* Menu */
.menu {
  display: flex;
  justify-content: center;
  background-color: #b7c3c6;
  padding: 10px 0;
  border-radius: 10px;
  margin: 20px auto;
  max-width: 600px;
  box-shadow: 0 4px 6px rgba(10, 91, 149, 0.244);
  transition: background-color 0.3s;
}

.page-container.dark-mode .menu {
  background-color: #2b2b3a;
}

.menu a {
  color: rgb(30, 26, 26);
  text-decoration: none;
  font-weight: bold;
  padding: 10px 20px;
  border-radius: 30px;
  transition: background-color 0.3s, transform 0.2s, color 0.3s;
}

.page-container.dark-mode .menu a {
  color: #e0e0e0;
}



/* Centered image */
.center-screen {
  height: 80vh;
  display: flex;
  justify-content: center;
  align-items: center;
  margin-top: 20px;
}

.center-screen img {
  width: 500px;
  height: auto;
  border-radius: 8px;
  border: 3px solid rgb(1, 2, 12);
  transition: border-color 0.3s;
}

.page-container.dark-mode .center-screen img {
  border-color: #e0dbdb;
}
</style>