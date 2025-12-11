<template>
  <div :class="['page-container', { 'dark-mode': isDarkMode }]">

    <!-- Navigation Menu -->
    <nav class="menu">
      <router-link to="/Genu">Home</router-link>
      <router-link to="/About">About</router-link>
      <router-link to="/Contact">Contact</router-link>
      <router-link to="/Projects">Projects</router-link>
    </nav>

    <!-- Mode Button -->
    <button id="mode-toggle" @click="toggleMode">
      <span v-if="isDarkMode">🌙</span>
      <span v-else>☀️</span>
    </button>

    <!-- Contact Heading -->
    <h2 class="contact-heading">You can contact me on the following:</h2>

    <!-- Contact Table -->
    <table class="contact-box">
  <thead>
    <tr>
      <th>Method</th>
      <th>Details</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Email</td>
     <td><a href="mailto:sihle@afrigis.co.za">sihle@afrigis.co.za</a></td>
    </tr>
    <tr>
      <td>Phone</td>
      <td>078 520 4433</td>
    </tr>
    <tr>
      <td>WhatsApp</td>
      <td><a href="https://wa.me/27732723384" target="_blank">073 272 3384</a></td>
    </tr>
  </tbody>
</table>

    <!-- Contact Form -->
    <div class="form-container">
      <h2>Send Me a Query</h2>
      <form @submit.prevent="submitForm">
        <input type="text" v-model="form.name" placeholder="Name and Surname" required />
        <input type="text" v-model="form.email" placeholder="Email" required />
        <input type="tel" v-model="form.cellnumber" placeholder="Cell Number" required pattern="[0-9]{10}" />
        <textarea v-model="form.query" placeholder="Your Query" required></textarea>
        <button type="submit">Submit</button>
      </form>
      <p v-if="submitted" class="success-message">Thank you! Your query has been submitted.</p>
    </div>

  </div>
</template>

<script setup>
import { ref, reactive } from "vue";

// Dark mode toggle
const isDarkMode = ref(false);
const toggleMode = () => {
  isDarkMode.value = !isDarkMode.value;
};

// Form reactive data
const form = reactive({
  name: '',
  Email: '',
  cellnumber: '',
  query: ''
});
const submitted = ref(false);

// Submit form
const submitForm = () => {
  console.log('Form submitted:', form);
  submitted.value = true;

  // Clear form
  form.name = '';
  form.Email = '';
  form.cellnumber = '';
  form.query = '';
};
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

/* DARK MODE */
.page-container.dark-mode {
  background-color: #1e1e2f;
  color: #e0e0e0;
}

/* MENU */
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

.page-container.dark-mode .menu {
  background-color: #2b2b3a;
}

.menu a {
  color: rgb(11, 10, 10);
  text-decoration: none;
  font-weight: bold;
  padding: 8px 16px;
  border-radius: 5px;
  transition: background-color 0.3s, color 0.3s;
}

.menu a:hover {
  background-color: rgba(255, 255, 255, 0.2);
}

.page-container.dark-mode .menu a {
  color: #e0e0e0;
}

/* CONTACT HEADING */
.contact-heading {
  color: #023445;
  margin: 20px 0;
}

.page-container.dark-mode .contact-heading {
  color: #ffffff;
}

/* CONTACT TABLE */
.contact-box {
  width: 100%;
  max-width: 1000px;
  margin: 0 auto;
  border-collapse: collapse;
}

.contact-box th,
.contact-box td {
  border: 1px solid #000;
  padding: 10px;
  text-align: left;
}

.contact-box th {
  background-color: #0c4f5f;
  color: white;
}

.contact-box td {
  background-color: #f3f3f3;
}

.page-container.dark-mode .contact-box td {
  background-color: #2b2b3a;
  color: #e0e0e0;
}

/* FORM STYLING */
.form-container {
  max-width: 600px;
  margin: 30px auto;
  padding: 20px;
  background-color: rgba(12, 79, 95, 0.1);
  border-radius: 15px;
  text-align: center;
}

.form-container input,
.form-container textarea {
  width: 90%;
  padding: 10px;
  margin: 8px 0;
  border-radius: 8px;
  border: 1px solid #888;
}

.form-container textarea {
  min-height: 100px;
  resize: vertical;
}

.form-container button {
  padding: 10px 20px;
  border: none;
  border-radius: 8px;
  background-color: #0c4f5f;
  color: white;
  cursor: pointer;
  transition: background-color 0.3s;
}

.form-container button:hover {
  background-color: #066a94;
}

.success-message {
  margin-top: 10px;
  color: green;
  font-weight: bold;
}

/* Dark mode adjustments */
.page-container.dark-mode .form-container {
  background-color: rgba(255, 255, 255, 0.1);
}

.page-container.dark-mode .form-container input,
.page-container.dark-mode .form-container textarea {
  background-color: rgba(255,255,255,0.1);
  color: white;
  border: 1px solid #fff;
}

.page-container.dark-mode .form-container button {
  background-color: #333;
}

.page-container.dark-mode .form-container button:hover {
  background-color: #555;
}
</style>
