<template>
    <div>
        <h4>Click Counter</h4>
        <p>Click on the following area to increase the counter</p>
        <div class="click-area" @click="incrementCount">Clicked {{ count }} times</div>
    </div>
</template>

<script>
/* eslint-disable */
import useCounter from './compositions/useCounter';
export default {
    name: 'ClickCounter',
    setup() {
        const { count, incrementCount } = useCounter(100, 10)
        return {
            count,
            incrementCount
        }
    }
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