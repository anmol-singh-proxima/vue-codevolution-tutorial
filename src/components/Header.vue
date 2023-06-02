<template>
    <div class="header-main">
        <div class="left-side">
            <h4>Vue Learning - Codevolution</h4>
        </div>
        <div class="right-side">
            <h4>Anmol Singh</h4>
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
    display: grid;
    color: #333;
    background-color: lightskyblue;
    height: 50px;
    align-items: center;
}
.header .left-side {
    grid-column: 1/2;
    grid-row: 1/2;
    text-align: left;
    padding-left: 20px;
}
.header .right-side {
    grid-column: 2/3;
    grid-row: 1/2;
    text-align: right;
    padding-right: 20px;
}
.header h4 {
    padding: 0;
    margin: 0;
    font-size: 17px;
}
</style>