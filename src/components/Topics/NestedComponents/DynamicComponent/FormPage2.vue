<template>
    <div class="form-contact">
        <label for="">Enter Email Id</label>
        <input type="email" id="" placeholder="i.e. anmol@gmail.com" />
        <label for="">Enter Phone number</label>
        <input type="text" id="" placeholder="i.e. 8945673489" />
    </div>
</template>

<script>
export default {
    name: 'FormPage2'
}
</script>

<style scoped>
.form-contact input {
    text-align: left;
    display: block;
    font-size: 13px;
    line-height: 1.3;
    padding: 6px 12px;
    margin-bottom: 15px;
    border: 1px solid rgba(100,100,100,0.5);
}
.form-contact label {
    text-align: left;
    display: block;
    font-size: 13px;
    margin-bottom: 10px;
}
</style>