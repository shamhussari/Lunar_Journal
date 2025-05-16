<template>
<section>
  <h2>Affirmations</h2>

  <!-- Display each affirmation; changes style when clicked -->
  <div
    v-for="(affirmation, index) in affirmations"
    :key="index"
    @click="markAsRead(index)"
    :class="['affirmation', { read: clicked[index] }]"
  >
    {{ affirmation }}
  </div>
</section>
</template>

<script>
import { ref } from 'vue'

export default {
name: 'Affirmations',
setup() {
  // List of celestial affirmations
  const affirmations = [
    "I am grounded and at peace.",
    "My mind is clear, and my heart is open.",
    "Today will be full of light and calm.",
    "I am capable of beautiful things."
  ]

  //  Tracks which affirmations were clicked
  const clicked = ref([])

  //  Marks an affirmation as read (clicked)
  const markAsRead = (index) => {
    clicked.value[index] = true
  }

  return { affirmations, clicked, markAsRead }
}
}
</script>

<style scoped>
/* Styling each affirmation block */
.affirmation {
background: radial-gradient(circle at center, #1c2b40 0%, #0f1b2c 100%);
margin: 0.75rem 0;
padding: 1.25rem;
border-radius: 12px;
cursor: pointer;
transition: 0.4s ease-in-out;
box-shadow: 0 0 12px rgba(150, 180, 255, 0.1);
color: #e6f2ff;
font-style: italic;
font-size: 1.1rem;
text-shadow: 0 0 6px rgba(255, 255, 255, 0.08);
}

/* ✦ Glow effect on hover */
.affirmation:hover {
box-shadow: 0 0 20px rgba(170, 220, 255, 0.3);
transform: translateY(-2px);
}

/* ✦ Visually marks read affirmations */
.read {
background: #3a5c83;
}
</style>