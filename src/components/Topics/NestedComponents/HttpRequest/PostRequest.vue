<template>
    <div class="post-request">
        <h3>POST Rquest to JSON-placeholder</h3>
        <div class="success" v-if="success">
            {{ success.message }}
        </div>
        <div class="error" v-if="error">
            {{ error.code }} - {{ error.name }}: {{ error.message }}
        </div>
        <form @submit.prevent="postRequest">
            <p><b>Enter Post Details:</b></p>
            <label for="id">Post Id</label>
            <input type="text" id="id" v-model="post.id" />
            <label for="title">Title</label>
            <input type="text" id="title" v-model="post.title" />
            <label for="body">Body</label>
            <input type="text" id="body" v-model="post.body" />
            <button type="submit">Submit Post</button>
        </form>
    </div>
</template>

<script>
/* eslint-disable */
import axios from 'axios'
export default {
    name: 'PostRequest',
    data() {
        return {
            post: {
                id: '',
                title: '',
                body: '',
            },
            success: null,
            error: null
        }
    },
    methods: {
        postRequest() {
            axios.post('https://jsonplaceholder.typicode.com/posts', this.post).then(response => {
                if(response.status === 201)
                this.success = {
                    message: `Status 201: Data Posted Successfully!!`,
                    data: response.data
                }
            }).catch(error => {
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
.success {
    background-color:green;
    border: 1px solid green;
}
.error {
    background-color: indianred;
    border: 1px solid indianred;
}
.post-request input, .post-request button {
    font-size: 13px;
    line-height: 1.3;
    padding: 6px 12px;
    display: block;
    border: 1px solid #999;
    margin-bottom: 15px;
}
 .post-request label {
    font-size: 13px;
    font-weight: 600;
    display: block;
    margin-bottom: 5px;
}
.post-request button {
    font-size: 14px;
}
.success, .error {
    font-size: 14px;
    line-height: 1.3;
    padding: 15px;
    margin-top: 20px;
    color: #fff;
    width: 400px;
    text-align: center;
}
</style>