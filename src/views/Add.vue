<template>
    <h2>Addコンポーネント</h2>
    <v-container>
        <CreateBook />
    </v-container>
</template>
<script>
import CreateBook from '../components/CreateBook.vue'

export default {
    name: 'Add',
    components: {
        CreateBook
    }
}
</script>