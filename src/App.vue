<script setup>
import { onMounted, ref } from 'vue';

const books = ref([]);
const username = 'admin';
const password = '1234';
const newBook = ref({
  title: '',
});

onMounted(async () => {
  try {
    

    const response = await fetch('http://localhost:8080/customer/books', {
      
    });

    if (response.ok) {
      const data = await response.json();
      books.value = data;
    } else {
      console.error('Failed to fetch data.');
    }
  } catch (error) {
    console.error('An error occurred:', error);
  }
});

const addBook = async () => {
  try {
    const base64Credentials = btoa(`${username}:${password}`);
    const response = await fetch('http://localhost:8080/admin/addbook', {
      method: 'PUT',
      headers: {
        'Authorization': `Basic ${base64Credentials}`,
        'Content-Type': 'application/json',
      },
      body: JSON.stringify(newBook.value),
    });

    if (response.ok) {
      console.log('Book added successfully');
    } else {
      console.error('Failed to add book.');
    }
  } catch (error) {
    console.error('An error occurred:', error);
  }
};
</script>

<template>
  <h1>Add a Book</h1>
  <form @submit.prevent="addBook">
    <label for="title">Title:</label>
    <input type="text" id="title" v-model="newBook.title" required />
    <button type="submit">Add Book</button>
  </form>
  <h2>Book List</h2>
  <ul>
    <li v-for="book in books" :key="book.id">
      {{ book.title }}
    </li>
  </ul>

  
</template>
