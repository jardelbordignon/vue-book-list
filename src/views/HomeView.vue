<script setup>
import { reactive } from 'vue'

// ref para tipos primitivos como number, string, boolean
//const count = ref(0)

// reactive para objetos
const courses = reactive([{ title: 'Vue 3' }, { title: 'React' }, { title: 'Node' }])

let newCourse = {}

// function increment() {
//   count.value++
// }

function addCourse() {
  courses.push(newCourse)
  newCourse = {}
}
</script>

<template>
  <div>
    <h1>Courses List</h1>

    <ul>
      <li v-for="course in courses" :key="course.title">
        <p>{{ course.title }}</p>
      </li>
    </ul>

    <br />

    <input type="text" v-model="newCourse.title" />
    <button type="button" @click="addCourse">Adicionar</button>
  </div>
</template>
