<template>
    <div class="get-request">
        <h3>GET Rquest to JSON-placeholder</h3>
        <button @click="getRequest">Get Posts</button>
        <div class="error" v-if="error">
            {{ error.code }} - {{ error.name }}: {{ error.message }}
        </div>
        <div class="posts">
            <div class="post" v-for="post in posts" :key="post.id">
                <p><b>{{ post.id }}. {{ post.title }}</b></p>
                <p>{{ post.body }}</p>
            </div>
        </div>
    </div>
</template>

<script>
/* eslint-disable */
import axios from 'axios'
export default {
    name: 'GetRequest',
    data() {
        return {
            posts: [],
            error: null
        }
    },
    methods: {
        getRequest() {
            axios.get('https://jsonplaceholder.typicode.com/posts')
            .then((response) => {
                if(response.status === 200) {
                    this.posts = response.data
                }
                console.log("Response:", response)
                console.log("Posts:", response.data)
            }).catch((error) => {
                this.error = {
                    code: error.code,
                    name: error.name,
                    message: error.message,
                }
            })
        }
    }
}
</script>

<style scoped>
.get-request button {
    font-size: 14px;
    line-height: 1.3;
    padding: 6px 12px;
    border: 1px solid #999;
}
.error {
    font-size: 14px;
    line-height: 1.3;
    padding: 15px;
    margin-top: 20px;
    color: #fff;
    width: 400px;
    text-align: center;
    background-color: indianred;
    border: 1px solid indianred;
}
.posts {
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    margin-top: 15px;
}
.post {
    width: 295px;
    border: 1px solid #999;
    padding: 10px;
    margin-right: 10px;
    margin-bottom: 10px;
}
.post p {
    font-size: 13px;
    line-height: 1.2;
}
</style>