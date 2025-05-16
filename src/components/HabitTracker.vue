<template>
<section>
  <h2>Habit Tracker</h2>

  <!-- Input field to add a new habit -->
  <input
    v-model="newHabit"
    @keyup.enter="addHabit"
    placeholder="Add a new habit"
  />

  <!-- List of habits, clickable to toggle completion -->
  <ul>
    <li
      v-for="(habit, index) in habits"
      :key="index"
      :class="{ completed: completed.includes(index) }"
      @click="toggleComplete(index)"
    >
      {{ habit }}
    </li>
  </ul>
</section>
</template>

<script>
import { ref } from 'vue'

export default {
name: 'HabitTracker',
setup() {
  const newHabit = ref('')
  const habits = ref([])
  const completed = ref([])

  // Add a habit if the input isn't empty
  const addHabit = () => {
    if (newHabit.value.trim()) {
      habits.value.push(newHabit.value.trim())
      newHabit.value = ''
    }
  }

  // Toggle completion state of a habit
  const toggleComplete = (index) => {
    if (completed.value.includes(index)) {
      completed.value = completed.value.filter(i => i !== index)
    } else {
      completed.value.push(index)
    }
  }

  return { newHabit, habits, completed, addHabit, toggleComplete }
}
}
</script>

<style scoped>
section {
margin-top: 2rem;
}

input {
width: 100%;
padding: 0.8rem;
border-radius: 8px;
border: none;
background-color: #223344;
color: #f0f4fa;
font-family: 'Times New Roman', serif;
font-weight: 200;
box-shadow: 0 0 10px rgba(140, 180, 255, 0.1);
transition: box-shadow 0.3s;
}

input::placeholder {
color: #9db1c7;
}

input:focus {
outline: none;
box-shadow: 0 0 15px rgba(180, 220, 255, 0.25);
}

ul {
  padding: 0;
  list-style: none;
  display: flex;
  flex-direction: column;
  gap: 1.2rem; 
}

li {
  background-color: #1c2d3a;
  padding: 1rem 1.5rem; 
  border-radius: 6px;
  cursor: pointer;
  color: #f0f4fa;
  font-weight: 300;
  transition: background 0.3s, box-shadow 0.3s;
  box-sizing: border-box;
}

li:hover {
box-shadow: 0 0 10px #8faed0;
}

li.completed {
background-color: #3b5b78;
text-decoration: line-through;
color: #b0cbe6;
}
</style>