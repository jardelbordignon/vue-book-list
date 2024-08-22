<script setup>
defineProps({
  courses: Array
})
</script>

<template>
  <div>
    <p>Courses {{ courses.length }}</p>
  </div>
</template>

<style scoped></style>
