<script setup>
import { defineProps, computed } from 'vue'

const props = defineProps({
  courses: Array
})

const coursesDone = computed(() => props.courses.filter(({ done }) => done).length)
</script>

<template>
  <div>
    <p>{{ `${coursesDone} cursos completos de um total de ${courses.length}` }}</p>
  </div>
</template>

<style scoped></style>
