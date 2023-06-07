<template>
    <div class="provide-inject">
        <p>This is ProvideInjectComponent, and it provides a value which will be injected into ComponentC and displayed there.</p>
        <h4>Increment Count</h4>
        <p>Count: {{ count }}</p>
        <button @click="incrementCount">Increment Count</button>
        <h4>Update Superhero Profile</h4>
        <input type="text" placeholder="Name" v-model="name" />
        <input type="text" placeholder="Heroname" v-model="heroname" />
        <input type="text" placeholder="Superpower" v-model="superpower" />
        <ComponentA />
    </div>
</template>

<script>
/* eslint-disable */
import { ref, reactive, toRefs, provide } from 'vue'
import ComponentA from './ProvideInject/ComponentA.vue';
export default {
    name: 'ProvideInject',
    components: {
        ComponentA,
    },
    setup() {
        // Ref value
        const count = ref(0)
        function incrementCount() {
            count.value++
        }

        // Reactive value
        const profile = reactive({
            name: '',
            heroname: '',
            superpower: '',
        })

        // Provide values
        provide('count', count)
        provide('profile', profile)
        provide('incrementCount', incrementCount)

        return {
            count,
            ...toRefs(profile),
            incrementCount,
        }
    }
}
</script>

<style scoped>
.provide-inject input, .provide-inject button {
    display: block;
    font-size: 14px;
    line-height: 1.3;
    padding: 6px 12px;
    margin-bottom: 10px;
    border: 1px solid #999;
}
</style>