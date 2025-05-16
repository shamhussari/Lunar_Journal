<template>
<div id="app">
  <!-- All main sections of the app are loaded here as components -->
  <Affirmations />
  <MoodTracker />
  <Reflection />
  <JournalEntry />
  <HabitTracker />
</div>
</template>

<script>
// Importing all components used in the SPA
import Affirmations from './components/Affirmations.vue'
import MoodTracker from './components/MoodTracker.vue'
import Reflection from './components/Reflection.vue'
import JournalEntry from './components/JournalEntry.vue'
import HabitTracker from './components/HabitTracker.vue'


export default {
name: 'App',
components: {
  Affirmations,
  MoodTracker,
  Reflection,
  JournalEntry,
  HabitTracker,

}
}
</script>

<style>
/* Importing Italiano font for headings */
@import url('https://fonts.googleapis.com/css2?family=Italianno&display=swap');

/* Global body styling with celestial dark blue gradient */
body {
background: linear-gradient(to bottom right, #02050e, #0c1c2c, #121e36);
color: #f0f8ff; 
font-family: "Times New Roman", serif;
margin: 0;
padding: 0;
background-attachment: fixed;
background-repeat: no-repeat;
background-size: cover;
}

/* Styling for the main content cards */
/* Cards have a radial gradient with a light center and dark edges for depth */
.card {
background: radial-gradient(circle at center, #1a2a40 0%, #0c1c2c 60%, #02050e 100%);
border-radius: 20px;
padding: 30px;
margin-bottom: 30px;
box-shadow: 0 0 25px rgba(180, 200, 255, 0.1),
 0 0 40px rgba(200, 220, 255, 0.08); /* subtle moon mist glow */
backdrop-filter: blur(10px);
transition: all 0.4s ease-in-out;
}

/* Card hover effect to enhance glow and slight scale */
.card:hover {
box-shadow: 0 0 30px rgba(255, 255, 255, 0.15),
 0 0 60px rgba(140, 200, 255, 0.25);
transform: translateY(-5px) scale(1.02);
}

/* Headings styled with cursive Italiano font and glow */
h2 {
font-family: "Italianno", cursive;
font-size: 3.2rem;
color: #e0ecff;
text-align: center;
text-shadow: 0 0 12px rgba(255, 255, 255, 0.3);
margin-bottom: 1rem;
}

/* Paragraph styling */
p {
font-size: 1.15rem;
color: #dce8f2;
line-height: 1.6;
margin-top: 12px;
text-shadow: 0 0 5px rgba(255, 255, 255, 0.05);
}

/* Styling for content sections */
section {
padding: 2.5rem;
margin: 2.5rem 0;
border-radius: 16px;
background-color: rgba(255, 255, 255, 0.04);
box-shadow: 0 0 20px rgba(140, 180, 255, 0.15);
transition: 0.3s ease-in-out;
}

/* Subtle glow effect on section hover */
section:hover {
box-shadow: 0 0 35px rgba(160, 210, 255, 0.2);
}

/* Button styling - celestial blue tone */
button {
background-color: #2b3a55;
border: none;
padding: 0.75rem 1.5rem;
border-radius: 12px;
color: #f0f8ff;
font-weight: bold;
cursor: pointer;
transition: all 0.3s ease-in-out;
margin-top: 1rem;
box-shadow: 0 0 12px rgba(173, 216, 255, 0.2);
}

/* Button hover and active states */
button:hover {
background-color: #384e72;
box-shadow: 0 0 20px rgba(200, 230, 255, 0.4);
}

button:active {
background-color: #1f2d45;
transform: scale(0.96);
}

/* Inputs and textarea with dark backgrounds and subtle glow */
input, textarea {
width: 100%;
padding: 1rem;
background-color: rgba(15, 25, 40, 0.9);
border: 1px solid #5a7598;
color: #f0f8ff;
border-radius: 10px;
margin-top: 1rem;
font-size: 1rem;
box-shadow: 0 0 10px rgba(180, 200, 255, 0.08);
}

/* Placeholder text styling */
input::placeholder,
textarea::placeholder {
color: #b0c4de;
}
</style>