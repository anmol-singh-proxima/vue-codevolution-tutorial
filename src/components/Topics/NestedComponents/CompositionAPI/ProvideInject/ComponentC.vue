<template>
    <div class="component-c">
        <h4>Component C</h4>
        <p>This is ComponentC containing a value provided from ProvideInjectComponent and injected here.</p>
        <h4>Increment Count</h4>
        <p>Count: {{ count }}</p>
        <button @click="incrementCount">Increment Count</button>
        <h4>Update Superhero Profile</h4>
        <p>Name: {{ name }}</p>
        <p>Heroname: {{ heroname }}</p>
        <p>Superpower: {{ superpower }}</p>
    </div>
</template>

<script>
/* eslint-disable */
import { inject, toRefs } from 'vue';
export default {
    name: 'ComponentB',
    setup() {
        // Injected Values
        const count = inject('count', 0)
        const profile = inject('profile', {})
        const incrementCount = inject('incrementCount')

        return {
            count,
            ...toRefs(profile),
            incrementCount,
        }
    }
}
</script>

<style scoped>
.component-c {
    border: 1px solid #999;
    padding: 20px;
    width: 100%;
    margin-top: 20px;
}
.component-c button {
    display: block;
    font-size: 14px;
    line-height: 1.3;
    padding: 6px 12px;
    margin-bottom: 10px;
    border: 1px solid #999;
}
</style>

