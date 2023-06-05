<template>
    <div>
        <h2>Http Requests</h2><hr/>
        <PostRequest /><hr/>
        <GetRequest />
    </div>
</template>

<script>
/* eslint-disable */
import GetRequest from './NestedComponents/HttpRequest/GetRequest.vue'
import PostRequest from './NestedComponents/HttpRequest/PostRequest.vue'
export default {
    name: 'HttpRequest',
    components: {
        GetRequest,
        PostRequest,
    },  
}
</script>

<style scoped>
</style>