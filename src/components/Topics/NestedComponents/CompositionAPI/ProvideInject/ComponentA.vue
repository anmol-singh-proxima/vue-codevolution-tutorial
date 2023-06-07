<template>
    <div class="component-a">
        <h4>Component A</h4>
        <p>This is ComponentA containing ComponentB</p>
        <ComponentB />
    </div>
</template>

<script>
/* eslint-disable */
import ComponentB from './ComponentB.vue';
export default {
    name: 'ComponentA',
    components: {
        ComponentB,
    },
}
</script>

<style scoped>
.component-a {
    border: 1px solid #999;
    padding: 20px;
    width: 100%;
    margin-top: 20px;
}
</style>