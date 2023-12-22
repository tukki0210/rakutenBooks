<template>
    <h2>Homeコンポーネント</h2>
    <v-container>
        <Book v-for="book in booksList" v-bind:book="book" />
    </v-container>
</template>
<script>
import Book from '../components/Book.vue';
import axios from 'axios';

export default {
    name: 'Home',
    components: {
        Book
    },
    data() {
        return {
            booksList: []
        }
    },
    async mounted() {
        const url = 'http://127.0.0.1:8000/api/books';
        const response = await axios.get(url)
        const booksList = response.data
        this.booksList = booksList
    }
}
</script>