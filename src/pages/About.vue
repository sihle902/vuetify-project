<template>
  <div :class="['page-container', { 'dark-mode': isDarkMode }]">

    <!-- Navigation -->
    <nav class="menu">
      <router-link to="/Genu">Home</router-link>
      <router-link to="/about">About</router-link>
      <router-link to="/contact">Contact</router-link>
      <router-link to="/projects">Projects</router-link>
    </nav>

    <!-- Banner -->
    <div class="about-banner">
      Get to know Sihle Genu
    </div>

    <!-- Mode Toggle -->
    <button id="mode-toggle" @click="toggleMode">
  <span v-if="isDarkMode">🌙</span>
<span v-else>☀️</span>          <!-- Sun icon for light mode -->
</button>

    <!-- About Content -->
    <div class="about-content">
      I’m a 24-year-old System Developer at Afrigis, passionate about creating smart, scalable, and user-focused digital solutions. I specialize in writing clean, efficient code and enjoy turning innovative ideas into functional systems that deliver real impact.

I attended high school at Watershed and studied Information and Communications Technology at Walter Sisulu University, which laid the foundation for my technical skills and problem-solving mindset.

Driven by continuous learning, I stay curious about emerging tools, technologies, and industry best practices. I thrive in problem-solving environments and enjoy collaborating with teams to deliver reliable, high-quality software. My goal is to grow as a developer while contributing meaningful and innovative solutions to every project I undertake.

    </div>
    

    <!-- SLIDESHOW / CAROUSEL -->
    <v-carousel>
      <v-carousel-item
        v-for="(image, i) in images"
        :key="i"
        :src="image"
      ></v-carousel-item>
    </v-carousel>
  </div>
</template>

<script setup>
import { ref } from 'vue';

// Dark mode
const isDarkMode = ref(false);
const toggleMode = () => {
  isDarkMode.value = !isDarkMode.value;
};

// IMAGES FOR CAROUSEL
const images = [
  '/image1.jpg',
  '/image2.jpg',
  '/image3.jpg',
  '/image4.jpg',
  '/public/image5.jpg',
];
</script>

<style scoped>
.page-container {
  font-family: Verdana;
  padding: 20px;
  min-height: 100vh;
  background-color: #ffffff;
  color: #000000;
  transition: background-color 0.4s, color 0.4s;
}

/* Dark Mode */
.page-container.dark-mode {
  background-color: #051c2a;
  color: #e0e0e0;
}

/* Menu */
.menu {
  display: flex;
  justify-content: center;
  gap: 20px;
  background-color: #0c4f5f;
  padding: 10px 0;
  border-radius: 10px;
  margin-bottom: 20px;
  transition: background-color 0.4s;
}

.menu a {
  color: rgb(18, 15, 15);
  text-decoration: none;
  font-weight: bold;
  padding: 8px 16px;
  border-radius: 5px;
}

.menu a:hover {
  background-color: rgba(255, 255, 255, 0.2);
}

/* Banner */
.about-banner {
  background-color: rgb(2, 52, 69);
  color: white;
  padding: 10px 10px;
  border-radius: 15px;
  font-size: 22px;
  margin-bottom: 20px;
}

/* Content */
.about-content {
  background-color: rgb(2, 52, 69);
  color: white;
  padding: 15px 25px;
  border-radius: 15px;
  line-height: 1.6;
  margin-top: 20px;
}
</style>
