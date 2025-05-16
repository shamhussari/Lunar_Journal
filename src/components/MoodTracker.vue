<template>
<section>
  <h2>How are you feeling today?</h2>

  <!-- ⭒ Mood selection buttons -->
  <div class="mood-options">
    <button
      v-for="mood in moods"
      :key="mood"
      :class="['mood-btn', { selected: selectedMood === mood }]"
      @click="selectMood(mood)"
    >
      {{ mood }}
    </button>
  </div>
</section>
</template>

<script>
import { ref } from 'vue';

export default {
name: 'MoodTracker',
setup() {
  // ⭒ Mood options
  const moods = ['Gloomy', 'Balanced', 'Radiant'];

  // ⭒ Reactive reference for currently selected mood
  const selectedMood = ref(null);

  // ⭒ Mood selection handler
  const selectMood = (mood) => {
    selectedMood.value = mood;
  };

  return { moods, selectedMood, selectMood };
}
};
</script>

<style scoped>
.mood-options {
display: flex;
justify-content: center;
gap: 1rem;
margin-top: 1.5rem;
flex-wrap: wrap;
}

/* ⭒ Base mood button */
.mood-btn {
background-color: #1c2b40;
color: #f0f8ff;
padding: 0.75rem 1.5rem;
border: none;
border-radius: 12px;
cursor: pointer;
font-weight:100;
transition: all 0.3s ease-in-out;
box-shadow: 0 0 12px rgba(120, 160, 255, 0.1);
}

/* ⭒ Hover state with soft glow */
.mood-btn:hover {
background-color: #2b4160;
box-shadow: 0 0 16px rgba(180, 220, 255, 0.3);
}

/* ⭒ Highlight selected mood */
.selected {
background-color: #3a5c83;
box-shadow: 0 0 20px rgba(200, 240, 255, 0.4);
transform: scale(1.05);
}
</style>