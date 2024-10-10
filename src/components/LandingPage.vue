<script setup lang="ts">
defineEmits(['login'])

const testimonials = [
  {
    name: "John Doe",
    company: "Tech Innovators Inc.",
    text: "StartupIdeas.ai helped us find our next big product idea. Highly recommended!"
  },
  {
    name: "Jane Smith",
    company: "Future Ventures",
    text: "The AI-powered suggestions from StartupIdeas.ai are truly game-changing."
  },
  {
    name: "Mike Johnson",
    company: "Disrupt Co.",
    text: "We've used StartupIdeas.ai for our last three projects. It's become an essential tool for our ideation process."
  }
]
</script>

<template>
  <div class="landing-page">
    <header>
      <h1>StartupIdeas.ai</h1>
      <p class="tagline">Powering the next generation of innovation</p>
    </header>
    
    <main>
      <section class="hero">
        <h2>Welcome to StartupIdeas.ai</h2>
        <p>Experience the next generation of frontend tooling. It's fast!</p>
        <button @click="$emit('login')" class="login-button">Login</button>
      </section>

      <section class="testimonials">
        <h3>What Our Clients Say</h3>
        <div class="testimonial-grid">
          <div v-for="(testimonial, index) in testimonials" :key="index" class="testimonial">
            <p>"{{ testimonial.text }}"</p>
            <p class="author">- {{ testimonial.name }}, {{ testimonial.company }}</p>
          </div>
        </div>
      </section>
    </main>

    <footer>
      <p>&copy; 2023 StartupIdeas.ai. All rights reserved.</p>
      <nav>
        <a href="#">About</a>
        <a href="#">Contact</a>
        <a href="#">Privacy Policy</a>
      </nav>
    </footer>
  </div>
</template>

<style scoped>
/* Styles remain unchanged */
</style>