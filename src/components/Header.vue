<template>
    <div class="header-main">
        <div class="left-side">
            <h3>Vue Learning - Codevolution</h3>
        </div>
        <div class="right-side">
            <h3>Anmol Singh</h3>
        </div>
    </div>
</template>

<script>
/* eslint-disable */
export default {
    name: 'Header',
}
</script>

<style scoped>
.header-main {
    display: block;
    background-color: lightskyblue;
    color: #333;
    clear: both;
    overflow: hidden;
    padding: 10px;
    justify-content: center;
}
.header .left-side {
    float: left;
}
.header .right-side {
    float: right;
}
.header h3 {
    padding: 0;
    margin: 0;
}
</style>