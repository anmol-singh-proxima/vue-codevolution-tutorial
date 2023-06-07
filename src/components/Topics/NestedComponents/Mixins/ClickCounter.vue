<template>
    <div>
        <h3>Click Counter</h3>
        <p>Click on the following area to increase the counter</p>
        <div class="click-area" @click="increment">Clicked {{ count }} times</div>
    </div>
</template>

<script>
/* eslint-disable */
import CounterMixin from './mixin/counter'
export default {
    name: 'ClickCounter',
    mixins: [CounterMixin],
}
</script>

<style scoped>
.click-area {
    padding: 10px;
    font-size: 16px;
    line-height: 1.3;
    text-align: center;
    width: 400px;
    color: #fff;
    background-color: chocolate;
}
</style>