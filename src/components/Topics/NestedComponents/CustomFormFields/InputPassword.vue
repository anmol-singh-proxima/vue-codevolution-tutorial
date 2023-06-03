<template>
    <div>
        <input
        type="password"
        :value="modelValue"
        :placeholder="placeholder"
        @input="$emit('update:modelValue', $event.target.value)" />
    </div>
</template>

<script>
/* eslint-disable */
export default {
    name: 'InputPassword',
    props: {
        modelValue: String,
        placeholder: String,
    }
}
</script>

<style scoped>
input {
    display: block;
    width: 100%;
    font-size: 14px;
    line-height: 1.3;
    padding: 6px 12px;
    margin-bottom: 15px;
    border: 1px solid #888;
}
</style>