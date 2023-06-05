<template>
    <div class="form-name">
        <label for="">Enter Firstname</label>
        <input type="text" id="" placeholder="i.e. Anmol" />
        <label for="">Enter Lastname</label>
        <input type="text" id="" placeholder="i.e. Singh" />
    </div>
</template>

<script>
export default {
    name: 'FormPage1'
}
</script>

<style scoped>
.form-name input {
    text-align: left;
    display: block;
    font-size: 13px;
    line-height: 1.3;
    padding: 6px 12px;
    margin-bottom: 15px;
    border: 1px solid rgba(100,100,100,0.5);
}
.form-name label {
    text-align: left;
    display: block;
    font-size: 13px;
    margin-bottom: 10px;
}
</style>