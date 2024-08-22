<script setup>
import { ref } from 'vue'

// ref para tipos primitivos como number, string, boolean
const count = ref(0)

function increment() {
  count.value++
}
</script>

<template>
  <div>
    <h2>Hello Composition API</h2>
    <h1>Count: {{ count }}</h1>
    <!-- <button @click="count++">Increment</button> -->
    <button @click="increment">Increment</button>
  </div>
</template>
