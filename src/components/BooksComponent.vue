<script setup>
const props = defineProps({
  books: Array
})
</script>

<template>
  <div class="books-list">
    <div class="book" v-for="book in props.books" :key="book.id">
      <div class="readIt" v-if="book.isRead">
        <i class="fa-solid fa-eye"></i>
      </div>
      <div class="book-cover">
        <img :src="book.cover" :alt="book.title" />

        <button :class="{ isRead: book.isRead }" @click="$emit('toggleIsRead', book.id)">
          <i class="fa-solid fa-eye"></i>
          <span>{{ book.isRead ? 'Lido' : 'Ainda não li' }}</span>
        </button>
      </div>
      <div class="book-details">
        <p class="book-author">{{ book.author }}</p>
        <h3 class="book-title">{{ book.title }}</h3>
        <p><i class="fa-solid fa-hashtag icon"></i> {{ book.isbn }}</p>
      </div>
    </div>
  </div>
</template>
