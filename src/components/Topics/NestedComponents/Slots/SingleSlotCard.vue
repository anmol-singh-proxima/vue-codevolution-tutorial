<template>
    <div class="card">
        <slot>
            <h4>Default Content</h4><hr/>
            <p>This is default content in case no content has been passed from the Parent Component</p>
        </slot>
    </div>
</template>

<script>
/* eslint-disable */
export default {
    name: 'SingleSlotCard',
}
</script>

<style scoped>
.card {
    box-shadow: 0 4px 8px 0 rgba(130, 140, 150, 0.5);
    padding: 10px;
    margin: 20px 20px 20px 0;
    width: fit-content;
    width: 300px;
}
.card:hover {
    box-shadow: 0 8px 16px 0 rgba(130, 140, 150, 0.5);
}
.card h4 {
    padding: 0;
    margin: 0;
}
.card hr {
    color: #ddd;
}
</style>