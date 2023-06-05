<template>
    <div class="form-password">
        <label for="">Enter Password</label>
        <input type="password" id="" />
        <label for="">Confirm Password</label>
        <input type="password" id="" />
    </div>
</template>

<script>
/* eslint-disable */
export default {
    name: 'FormPage3'
}
</script>

<style scoped>
.form-password input {
    text-align: left;
    display: block;
    font-size: 13px;
    line-height: 1.3;
    padding: 6px 12px;
    margin-bottom: 15px;
    border: 1px solid rgba(100,100,100,0.5);
}
.form-password label {
    text-align: left;
    display: block;
    font-size: 13px;
    margin-bottom: 10px;
}
</style>