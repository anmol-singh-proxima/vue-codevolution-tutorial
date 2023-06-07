<template>
    <div>
        <p>The input will get focused as the page gets loaded using the Template Ref in Composition API </p>
        <input type="text" placeholder="Some Value" ref="inputRef" />
    </div>
</template>

<script>
/* eslint-disable */
import { ref, onMounted } from 'vue'
export default {
    name: 'TemplateRef',
    setup() {
        const inputRef = ref(null)
        onMounted(() => {
            inputRef.value.focus()
        })
        return {
            inputRef
        }
    }
}
</script>

<style scoped>
input {
    display: block;
    font-size: 14px;
    line-height: 1.3;
    padding: 6px 12px;
    margin-bottom: 10px;
    border: 1px solid #999;
}
</style>