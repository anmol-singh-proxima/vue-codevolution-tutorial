<template>
    <div>
        <p>This component watches the inputs for any change and the function to execute logs the changes in the Console Log.</p>
        <div>
            <h4>Watchers for Ref Inputs</h4>
            <input type="text" placeholder="Firstname" v-model="firstname" />
            <input type="text" placeholder="Lastname" v-model="lastname" />
        </div>
        <div>
            <h4>Watchers for Reactive Inputs</h4>
            <input type="text" placeholder="Reactive Firstname" v-model="reactFirstname" />
            <input type="text" placeholder="Reactive Lastname" v-model="reactLastname" />
            <input type="text" placeholder="Reactive Heroname" v-model="object.heroname" />
        </div>
    </div>
</template>

<script>
/* eslint-disable */
import { ref, reactive, toRefs, watch } from 'vue'
import _ from 'lodash'
export default {
    name: 'ReplaceWatchers',
    setup() {
        // Watchers for ref data
        const firstname = ref('')
        const lastname = ref('')
        watch([firstname, lastname], (newValues, oldValues) => {
            console.log("Firstname oldValue:", oldValues[0])
            console.log("Firstname newValue:", newValues[0])
            console.log("Lastname oldValue:", oldValues[1])
            console.log("Lastname newValue:", newValues[1])
        }, {
            immediate: true,
        })

        // Watchers for reactive data
        const state = reactive({
            reactFirstname: '',
            reactLastname: '',
            object: {
                heroname: ''
            }
        })
        // Watcher for whole state
        watch(() => {
            return {...state}
        }, (newValue, oldValue) => {
            console.log("Reactive Firstname oldValue:", oldValue.reactFirstname)
            console.log("Reactive Firstname newValue:", newValue.reactFirstname)
            console.log("Reactive Lastname oldValue:", oldValue.reactLastname)
            console.log("Reactive Lastname newValue:", newValue.reactLastname)
        })
        // Watcher for individual property of state
        watch(() => state.reactFirstname, (newValue, oldValue) => {
            console.log("Reactive Ind Firstname oldValue:", oldValue)
            console.log("Reactive Ind Firstname newValue:", newValue)
        })
        // Watcher for deep scan
        watch(() => _.cloneDeep(state.object), (newValue, oldValue) => {
            console.log("Reactive Heroname oldValue:", oldValue.heroname)
            console.log("Reactive Heroname newValue:", newValue.heroname)
        })

        // Return data
        return {
            firstname,
            lastname,
            ...toRefs(state),
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