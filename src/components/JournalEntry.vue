<template>
<section>
  <h2>Journal Entry</h2>
  <p>How was your day? What did you enjoy? What could’ve been better?</p>

  <!-- ⭒ Textarea where user writes their journal -->
  <textarea
    v-model="entry"
    rows="6"
    placeholder="Write your thoughts..."
  ></textarea>

  <!-- ⭒ Save button stores journal in localStorage -->
  <button @click="saveEntry">Save Entry</button>
</section>
</template>

<script>
import { ref } from 'vue'

export default {
name: 'JournalEntry',
setup() {
  // ⭒ Entry binds to textarea content
  const entry = ref('')

  // ⭒ Save journal entry to local storage
  const saveEntry = () => {
    localStorage.setItem('journalEntry', entry.value)
    alert('Entry saved ✧')
  }

  return { entry, saveEntry }
}
}
</script>

<style scoped>
/* ⭒ Styling the text area */
textarea {
width: 100%;
padding: 1rem;
margin-top: 1rem;
background-color: rgba(31, 47, 63, 0.95);
color: #f1f4f8;
border: none;
border-radius: 10px;
font-size: 1rem;
box-shadow: 0 0 12px rgba(150, 180, 255, 0.08);
}

/* ⭒ Styling the save button */
button {
margin-top: 1rem;
padding: 0.75rem 1.5rem;
background-color: #3c5d7c;
color: #f0f8ff;
border: none;
border-radius: 12px;
cursor: pointer;
font-weight: 150;
transition: all 0.3s ease-in-out;
box-shadow: 0 0 12px rgba(173, 216, 255, 0.2);
}

/* ⭒ Button hover glow */
button:hover {
background-color: #4d6e8e;
box-shadow: 0 0 18px rgba(200, 230, 255, 0.4);
}
</style>