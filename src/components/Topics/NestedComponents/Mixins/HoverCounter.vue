<template>
    <div>
        <h3>Hover Counter</h3>
        <p>Hover on the following area to increase the counter</p>
        <div class="hover-area" @mouseover="increment">Hovered {{ count }} times</div>
    </div>
</template>

<script>
/* eslint-disable */
import CounterMixin from './mixin/counter'
export default {
    name: 'HoverCounter',
    mixins: [CounterMixin],
}
</script>

<style scoped>
.hover-area {
    padding: 10px;
    font-size: 16px;
    line-height: 1.3;
    text-align: center;
    width: 400px;
    color: #fff;
    background-color: chocolate;
}
</style>