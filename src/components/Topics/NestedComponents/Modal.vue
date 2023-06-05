<template>
    <div class="modal-overlay" @click="$emit('close')">
        <div class="modal-content">
            <slot></slot>
            <button @click="$emit('close')">Close</button>
        </div>
    </div>
</template>

<script>
/* eslint-disable */
export default {
    name: 'Modal',
    emits: ['close']
}
</script>

<style scoped>
.modal-overlay {
    position: absolute;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    display: grid;
    justify-content: center;
    align-items: center;
    background-color: rgba(0, 0, 0, 0.3);
}  
.modal-content {
    font-family: "Fondamento", cursive;
    padding: 20px;
    background: #fff;
    border-radius: 2px;
    display: inline-block;
    min-height: 280px;
    margin: 1rem;
    min-width: 300px;
    width: 400px;
    position: relative;
    box-shadow: 0 3px 6px rgba(0, 0, 0, 0.16), 0 3px 6px rgba(0, 0, 0, 0.23);
    justify-self: center;
}
.modal-content button {
    font-size: 14px;
    padding: 6px 12px;
    line-height: 1.3;
}
</style>