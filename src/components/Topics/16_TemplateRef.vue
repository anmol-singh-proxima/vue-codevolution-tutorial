<template>
    <div>
        <h2>Template Ref</h2><hr/>
        <div class="template-ref">
            <p>This is a login form and by using the ref attribute on input html, we are focusing the cursor on the first input element as the component mounts on the UI.</p>
            <h3>Login Form</h3>
            <form>
                <input type="text" placeholder="Username" ref="inputRef" />
                <input type="password" placeholder="Password" />
                <button>Login</button>
            </form>
        </div>
    </div>
</template>

<script>
export default {
    name: 'TemplateRef',
    mounted() {
        this.$refs.inputRef.focus()
    }
}
</script>

<style scoped>
.template-ref input, .template-ref button {
    font-size: 14px;
    line-height: 1.3;
    padding: 6px 12px;
    border: 1px solid #999;
    margin-bottom: 15px;
    display: block;
}
</style>