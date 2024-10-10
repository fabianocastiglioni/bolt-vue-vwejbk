<script setup lang="ts">
import { ref } from 'vue'

defineEmits(['back'])

const username = ref('')
const password = ref('')

const handleSubmit = () => {
  // Here you would typically handle the login logic
  console.log('Login submitted', { username: username.value, password: password.value })
}
</script>

<template>
  <div class="login-page">
    <h2>Login</h2>
    <form @submit.prevent="handleSubmit">
      <div class="form-group">
        <label for="username">Username:</label>
        <input type="text" id="username" v-model="username" required>
      </div>
      <div class="form-group">
        <label for="password">Password:</label>
        <input type="password" id="password" v-model="password" required>
      </div>
      <button type="submit" class="submit-button">Submit</button>
    </form>
    <button @click="$emit('back')" class="back-button">Back to Landing Page</button>
  </div>
</template>

<style scoped>
.login-page {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 100vh;
}

h2 {
  margin-bottom: 1em;
}

.form-group {
  margin-bottom: 1em;
  text-align: left;
}

label {
  display: block;
  margin-bottom: 0.5em;
}

input {
  width: 100%;
  padding: 0.5em;
  font-size: 1em;
}

.submit-button, .back-button {
  font-size: 1em;
  padding: 0.6em 1.2em;
  margin-top: 1em;
  background-color: #42b883;
  color: white;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  transition: background-color 0.3s;
}

.submit-button:hover, .back-button:hover {
  background-color: #3aa876;
}

.back-button {
  background-color: #64748b;
  margin-top: 1em;
}

.back-button:hover {
  background-color: #475569;
}
</style>