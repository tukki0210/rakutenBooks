<template>
    <v-card class="ma-2 pa-2">
        <h3>本の登録</h3>
        <div>
            <label for="title">タイトル：</label>
            <input type="text" id="title" v-model="title">
        </div>
        <div>
            <label for="title">値段：</label>
            <input type="text" id="price" v-model="price">
        </div>
        <button v-on:click="doSubmit">送信</button>
    </v-card>

    <v-card class="ma-2 pa-2">
        <!-- この方法もあり -->
        <form action='http://127.0.0.1:8000/api/books'>
            <input type="text" id="title">
            <input type="submit" value="送信">
        </form>
    </v-card>
</template>
<script>
export default {
    name: "CreateBook",
    data() {
        return {
            title: '',
            price: ''
        }
    },
    methods:{
        async doSubmit(){
            console.log(this.title,this.price)
            const data = {
                title: this.title,
                price: this.price
            }

            const response = await fetch('http://127.0.0.1:8000/api/books',{
                method: "POST",
                headers: {
                    "Content-Type":"application/json"
                },
                body: JSON.stringify(data)
            })

            console.log(response)
        }
    }
}
</script>