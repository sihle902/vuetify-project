<template>
 <div :class="['page-container', { 'dark-mode': isDark }]">

    <!-- Toggle Button -->


    <!-- Header -->
    <h1 class="page-title">Welcome to my Projects</h1>
    <button id="mode-toggle" @click="toggleMode">
  <span v-if="isDark">🌙</span>  <!-- Moon icon for dark mode -->
  <span v-else>☀️</span>          <!-- Sun icon for light mode -->
</button>
    <nav class="menu">
  <router-link to="/Genu">Home</router-link>
  <router-link to="/about">About</router-link>
  <router-link to="/contact">Contact</router-link>
  <router-link to="/projects">Projects</router-link>
</nav>

    <!-- Project Section -->
    <div class="img-row">

      <div class="img-box">
        <img src="/Network project.jpg" alt="network project"width="300" height="300">
        <p class="img-text">
          This was a group Project were by we used Cisco Packet Tracer to create a structured secured network for a corporate business.
        </p>
      </div>

      
      <div class="img-box">
        <img src="/home affairs app.jpg" alt="home affairs app" width="300" height="300">
        <p class="img-text">
          This was a group project were by we created an API to help citizens to book a date of when they can do their IDs at Home Affairs.
        </p>
      </div>

      <div class="img-box">
        <img src="/business website.jpg" alt="business website" width="300" height="300">
        <p class="img-text">
         This was an individual project, I created a business website for a local clothing brand so that it can reach a wide variety of customers.
        </p>
      </div>

    </div>

    <!-- Navigation -->
     


  </div>
</template>

<script setup>
    
import { ref } from 'vue'

const isDark = ref(false)

const toggleMode = () => {
  isDark.value = !isDark.value
  document.body.classList.toggle('dark-mode', isDark.value)
}
</script>

<style >
.page-container {
  background-color: rgb(227, 231, 233);
  font-family: Verdana;
  text-align: center;
  min-height: 100vh;
  transition: background-color 0.3s, color 0.3s;
}

/* Dark mode styling */
.page-container.dark-mode {
  background-color: #0f0e0e;
  color: #e8e1e1;
}

.projects-page {
  text-align: center;
  font-family: Verdana;
  padding: 20px;
}

/* Header */
.page-title {
  background-color: rgb(6, 70, 86);
  color: rgb(201, 191, 191);
  padding: 15px;
  border-radius: 10px;
}

/* Image Layout */
.img-row {
  display: flex;
  justify-content: center;
  gap: 30px;
  margin: 30px 0;
}

.img-box {
  width: 300px;
}

.img-box img {
  width: 100%;
  height: 300px;
  object-fit: cover;
  border-radius: 10px;
  border: 3px solid rgb(211, 193, 193);
}

.img-text {
  background-color: rgba(0, 0, 0, 0.7); /* semi-transparent dark box */
  color: #fff;                          /* text color inside the box */
  padding: 12px 15px;                   /* space inside the box */
  border-radius: 10px;                  /* rounded corners */
  margin-top: 10px;                      /* spacing above each box */
  font-size: 18px;                       /* readable font size */
  text-align: center;                    /* center the text */
  box-shadow: 0 4px 6px rgba(0,0,0,0.3); /* subtle shadow for depth */
  transition: background-color 0.3s, color 0.3s, transform 0.3s;
}

/* Optional hover effect for interactivity */
.img-text:hover {
  transform: translateY(-3px);
  box-shadow: 0 6px 10px rgba(0,0,0,0.4);
}

/* Dark mode adjustment */
.page-container.dark-mode .img-text {
  background-color: rgba(241, 240, 236, 0.495);
  color: #ffffff;
}



/* Menu */
.menu {
  margin-top: 40px;
  display: flex;
  justify-content: center;
  gap: 20px;
}

.menu a {
  background-color: #0888bbe7;
  padding: 10px 18px;
  border-radius: 8px;
  font-weight: bold;
  text-decoration: none;
  color: black;
}



/* Dark Mode */
.dark-mode {
  background-color: #1e1e2f;
  color: white;
}

.dark-mode .page-title {
  background-color: #0a374d;
}

.dark-mode .img-box img {
  border-color: white;
}

.dark-mode .menu a {
  background-color: #333;
  color: rgb(196, 184, 184);
}

.dark-mode .menu a:hover {
  background-color: #555;
}
</style>
