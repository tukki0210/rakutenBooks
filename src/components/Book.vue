<template>
    <v-card class="ma-2 pa-2">
        <h3>{{ book.title }}</h3>
        <p>{{ book.price }}円</p>
    </v-card>
</template>
<script>
export default {
    name: "Book",
    props: {
        book: Object
    },
}
</script>