<template>
    <div>
        <p>Here, the profile details will change after 5 seconds</p>
        <h4>Profile:</h4>
        <p>Firstname: {{ firstname }}</p>
        <p>Lastname: {{ lastname }}</p>
        <p>Heroname: {{ heroname }}</p>
    </div>
</template>

<script>
/* eslint-disable */
import { reactive, toRefs } from 'vue'
export default {
    name: 'Torefs',
    setup() {
        const profile = reactive({
            firstname: 'Natasha',
            lastname: 'Romanoff',
            heroname: 'Black Widow',
        })

        setTimeout(() => {
            profile.firstname = 'Wanda'
            profile.lastname = 'Maximoff'
            profile.heroname = 'Scarlet Witch'
            console.log("profile:", profile)
        }, 5000)

        return toRefs(profile)
    }
}
</script>

<style scoped>

</style>