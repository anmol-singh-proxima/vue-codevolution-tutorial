<template>
    <div class="card">
        <div id="header">
            <slot name="header">Header</slot>
        </div>
        <div id="content">
            <slot name="content">Content</slot>
        </div>
        <div id="footer">
            <slot name="footer">Footer</slot>
        </div>
    </div>
</template>

<script>
/* eslint-disable */
export default {
    name: 'MultipleSlotCard'
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
.card #header {
    padding: 10px;
}
.card #content {
    padding: 10px;
    border-top: 1px solid #ddd;
    border-bottom: 1px solid #ddd;
}
.card #footer {
    padding: 10px;
}
</style>