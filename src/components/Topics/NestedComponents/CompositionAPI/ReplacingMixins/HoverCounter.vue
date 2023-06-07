<template>
    <div>
        <h4>Hover Counter</h4>
        <p>Hover on the following area to increase the counter</p>
        <div class="hover-area" @mouseover="incrementCount">Hovered {{ count }} times</div>
    </div>
</template>

<script>
/* eslint-disable */
import useCounter from './compositions/useCounter';
export default {
    name: 'HoverCounter',
    setup() {
        const { count, incrementCount } = useCounter()
        return {
            count,
            incrementCount
        }
    }
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