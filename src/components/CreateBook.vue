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
</template>
<script>
import axios from 'axios';

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
            const url = 'http://127.0.0.1:8000/api/books'

            // const response = await fetch('http://127.0.0.1:8000/api/books',{
            //     method: "POST",
            //     headers: {
            //         "Content-Type":"application/json"
            //     },
            //     body: JSON.stringify(data)
            // })

            // console.log(response)]

            await axios.post(url,data);
        }
    }
}
</script>