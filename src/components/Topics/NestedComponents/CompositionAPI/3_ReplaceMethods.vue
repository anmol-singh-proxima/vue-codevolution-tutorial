<template>
    <div>
        <p>Here, the functionality for Increment Counter and Changing Profile are individually together to make the code less complex</p>
        <h4>Increment Counter</h4>
        <p>Count: {{ count }}</p>
        <button @click="incrementCount">Increment Count</button>
        <h4>Change Profile</h4>
        <p>Firstname: {{ firstname }}</p>
        <p>Lastname: {{ lastname }}</p>
        <p>Heroname: {{ heroname }}</p>
        <button @click="changeProfile">Change Profile</button>
    </div>
</template>

<script>
/* eslint-disable */
import { ref, reactive, toRefs } from 'vue'
export default {
    name:'ReplaceMethods',
    setup() {
        // Increment Counter functionality
        const count = ref(0)
        function incrementCount() {
            count.value++
        }

        // Changing Profile functionality
        const profile = reactive({
            firstname: 'Natasha',
            lastname: 'Romanoff',
            heroname: 'Black Widow',
        })
        function changeProfile() {
            profile.firstname = 'Wanda'
            profile.lastname = 'Maximoff'
            profile.heroname = 'Scarlet Witch'
        }

        // Return data and functions
        return {
            count,
            incrementCount,
            ...toRefs(profile),
            changeProfile
        }
    }
}
</script>

<style scoped>
button {
    font-size: 14px;
    line-height: 1.3;
    padding: 6px 12px;
    margin-bottom: 10px;
    border: 1px solid #999;
}
</style>