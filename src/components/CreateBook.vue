<template>

</template>
<script>
export default {
    name:'CreateBook',
    data(){
        return {
           title:'',
           price:''
        }
    },
    async methods(){
        const url = 'http://127.0.0.1:8000/api/books';
        await fetch(url)
    }
}
</script>