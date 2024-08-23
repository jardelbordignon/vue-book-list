<script setup>
import { computed } from 'vue'

const props = defineProps({
  books: Array
})

const booksRead = computed(() => props.books.filter((book) => book.isRead).length)
const booksReadMessage = computed(() =>
  booksRead.value >= props.books.length
    ? 'Parabéns, todos os livros foram lidos!'
    : `${booksRead.value} de ${props.books.length} livros lidos`
)
</script>

<template>
  <div class="books-read">
    <label for="progress">Seu Progresso</label><br />
    <progress :value="booksRead" :max="books.length"></progress>
    <p>{{ booksReadMessage }}</p>
  </div>
</template>
