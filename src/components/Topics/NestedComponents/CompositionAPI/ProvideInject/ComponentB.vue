<template>
    <div class="component-b">
        <h4>Component B</h4>
        <p>This is ComponentB containing ComponentC</p>
        <ComponentC />
    </div>
</template>

<script>
/* eslint-disable */
import ComponentC from './ComponentC.vue';
export default {
    name: 'ComponentB',
    components: {
        ComponentC,
    },
}
</script>

<style scoped>
.component-b {
    border: 1px solid #999;
    padding: 20px;
    width: 100%;
    margin-top: 20px;
}
</style>
