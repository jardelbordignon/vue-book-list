<script setup>
import { ref, reactive } from 'vue'

import BookProgress from './components/BookProgress.vue'
import BooksComponent from './components/BooksComponent.vue'
import AddBookComponent from './components/AddBookComponent.vue'

const books = reactive([
  {
    id: 1,
    title: 'History of Europe',
    cover: 'https://m.media-amazon.com/images/I/71mMtk5i71L._AC_UF1000,1000_QL80_.jpg',
    isRead: true,
    isbn: '0-395-07157-8',
    author: 'Daniel Trejo'
  },
  {
    id: 2,
    title: 'Penguin Classics',
    cover: 'https://m.media-amazon.com/images/I/91cKrZxBuwL._AC_UF1000,1000_QL80_.jpg',
    isRead: false,
    isbn: '0-395-07157-8',
    author: 'Daniel Trejo, Jon Snow'
  },
  {
    id: 3,
    title: 'Becoming',
    cover: 'https://m.media-amazon.com/images/I/81KGjsBXQ7L._AC_UF1000,1000_QL80_.jpg',
    isRead: false,
    isbn: '0-395-07157-8',
    author: 'Daniel Trejo'
  },
  {
    id: 4,
    title: 'Sonnets',
    cover: 'https://whitegablespublishing.com/wp-content/uploads/2019/05/printpress-product-5.jpeg',
    isRead: false,
    isbn: '0-395-07157-8',
    author: 'Daniel Trejo'
  }
])

const showAddBook = ref(false)

const handleToggleIsRead = (bookId) => {
  const index = books.findIndex((book) => book.id === bookId)
  books[index].isRead = !books[index].isRead
}
</script>

<template>
  <div class="container" v-if="showAddBook">
    <AddBookComponent @closeAddBook="showAddBook = false" />
  </div>
  <div class="container" v-else>
    <h1>📖 Meus Livros</h1>
    <div class="header-btns">
      <button class="btn" @click="showAddBook = true">Adicionar Livro +</button>
    </div>

    <div class="books-container">
      <BooksComponent :books="books" @toggleIsRead="handleToggleIsRead" />
      <BookProgress :books="books" />
    </div>
  </div>
</template>

<style scoped></style>
