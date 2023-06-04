<template>
    <div class="article">
        <slot :article="article"></slot>
    </div>
</template>

<script>
/* eslint-disable */
export default {
    name: 'SlotPropComp',
    data() {
        return {
            article: {
                title: 'Some Random Title',
                author: 'Anmol Singh',
                date: '05/06/2023',
                content: 'This is a great article for the demo purpose but the topic is not decided and the content is just some rubbish whatever is coming in my mind. Thank you for reading this article very patiently. Happy to write this kind of articles again!',
                noOfLikes: '50',
                noOfDislikes: '10',
            }
        }
    }
}
</script>

<style scoped>
.article {
    box-shadow: 0 4px 8px 0 rgba(130, 140, 150, 0.5);
    padding: 10px;
    margin: 20px 20px 20px 0;
    width: fit-content;
    width: 300px;
}
</style>