<template>
<section>
  <!-- Title for the reflection section -->
  <h2>Today's Reflection</h2>
  <!-- Prompt to encourage the user to reflect -->
  <p>What's one thing that will make your day better?</p>
  
  <!-- Textarea bound to `reflection` via v-model for reactivity -->
  <textarea
    v-model="reflection"
    rows="4"
    placeholder="Write here..."
  ></textarea>
</section>
</template>

<script>
import { ref } from 'vue'

export default {
name: 'Reflection',
setup() {
  // Reactive variable to hold user reflection input
  const reflection = ref('')
  return { reflection }
}
}
</script>

<style scoped>
/* Styling the textarea to match the theme */
textarea {
width: 100%;
padding: 1rem;
border-radius: 6px;
border: none;
background-color: #1e2a38; 
color: #e0e6ed; 
margin-top: 1rem;
font-weight: 200; 
font-family: 'Times New Roman', serif;
box-shadow: 0 0 10px rgba(180, 200, 255, 0.05);
transition: 0.3s ease-in-out;
}

textarea::placeholder {
color: #a9bfd8;
}


textarea:focus {
outline: none;
box-shadow: 0 0 15px rgba(160, 200, 255, 0.2);
}
</style>