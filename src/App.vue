<script setup>
import { ref } from 'vue'

const newTask = ref('')
const list = ref([])
const addTask = () => {
  list.value.push(newTask.value)
}
</script>

<template>
  <div class="container">
    <div class="head">
      <h1 class="title">Todo List</h1>
    </div>
    <div class="header">
      <input
        v-model="newTask"
        type="text"
        name="taskAdd"
        placeholder="Write your task..."
      />
      <select name="select" id="select">
        <option value="all">All</option>
        <option value="complete">Complete</option>
        <option value="incomplete">Incomplete</option>
      </select>
      <button type="submit" class="btn" @click="addTask">Add task</button>
    </div>
    <div class="body">
      <!-- Здесь будут ваши задачи -->
      <ul>
        <li v-for="task in list" :key="task">
          {{ task }}
        </li>
      </ul>
    </div>
  </div>
</template>

<style scoped>
.container {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  max-width: 750px;
  margin: 0 auto;
  width: 100%;
  padding: 20px;
}

.head {
  width: 100%;
  text-align: center;
}

.title {
  text-transform: uppercase;
  font-family: 'Kanit', sans-serif;
  font-size: 26px;
  margin-top: 40px;
  margin-bottom: 18px;
  font-weight: 500;
}

.header {
  display: flex;
  gap: 15px;
  justify-content: center;
  align-items: center;
  width: 100%;
  margin-bottom: 30px;
  padding-right: 16px;
}

input {
  border: 1px solid #6c63ff;
  border-radius: 5px;
  width: 595px;
  height: 38px;
  padding: 0 15px;
  font-size: 14px;
  font-family: 'Inter', sans-serif;
  font-weight: 500;
  font-size: 16px;
}

input:focus {
  outline: none;
  border-color: #5a52d5;
}

select {
  width: 85px;
  height: 38px;
  background-color: #6c63ff;
  border-radius: 5px;
  color: white;
  border: 1px solid #6c63ff;
  padding: 0 10px;
  cursor: pointer;
  text-transform: uppercase;
  font-family: 'Kanit', sans-serif;
  font-size: 18px;
}

select:focus {
  outline: none;
}

.body {
  width: 100%;
  /* Добавьте стили для тела */
}

.btn {
  width: 85px;
  height: 38px;
  border-radius: 5px;
  color: white;
  border: 1px solid #6c63ff;
  background-color: #6c63ff;
  color: white;
  text-transform: uppercase;
  font-family: 'Kanit', sans-serif;
}
</style>