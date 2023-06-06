<template>
    <div>
        <p>Here, we are replacing computed propety of Options API with computed() function of Composition API</p>
        <h4>Form Inputs using ref()</h4>
        <form>
            <input type="text" placeholder="First name" v-model="refFirstname" />
            <input type="text" placeholder="Last name" v-model="refLastname" />
        </form>
        <p>Fullname: {{ refFullname }}</p>
        <h4>Form Inputs using reactive()</h4>
        <form>
            <input type="text" placeholder="First name" v-model="reactiveFirstname" />
            <input type="text" placeholder="Last name" v-model="reactiveLastname" />
        </form>
        <p>Fullname: {{ reactiveFullname }}</p>
    </div>
</template>

<script>
/* eslint-disable */
import { ref, reactive, toRefs, computed } from 'vue'
export default {
    name: 'ReplaceComputed',
    setup() {
        const refFirstname = ref('')
        const refLastname = ref('')
        const refFullname = computed(function() {
            return `${refFirstname.value} ${refLastname.value}`
        })

        const state = reactive({
            reactiveFirstname: '',
            reactiveLastname: '',
        })
        const reactiveFullname = computed(function() {
            return `${state.reactiveFirstname} ${state.reactiveLastname}`
        })

        return {
            refFirstname,
            refLastname,
            refFullname,
            ...toRefs(state),
            reactiveFullname
        }
    }
}
</script>

<style scoped>
input {
    display: block;
    font-size: 14px;
    line-height: 1.3;
    padding: 6px 12px;
    margin-bottom: 10px;
    border: 1px solid #999;
}
</style>