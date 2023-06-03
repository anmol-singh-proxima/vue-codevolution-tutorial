<template>
    <div class="article">
        <h4>{{ article.title }}</h4>
        <p>By <span>{{ article.author }}</span> on <span>{{ article.date }}</span></p>
        <p>{{ article.content }}</p>
        <button>Like</button>
        <button>Dislike</button>
    </div>
</template>

<script>
/* eslint-disable */
export default {
    name: 'Article',
    props: {
        article: {
            type: Object,
            required: true,
        }
    }
}
</script>

<style scoped>
.article {
    border: 1px solid #999;
    padding: 10px;
    width: 500px;
    margin-bottom: 10px;
}
.article p {
    font-size: 14px;
}
.article p span {
    font-size: 13px;
    font-style: italic;
    font-weight: 600;
}
.article button {
    display: inline-block;
    font-size: 12px;
    padding: 6px 12px;
    border: 1px solid #999;
    margin-right: 10px;
}
</style>