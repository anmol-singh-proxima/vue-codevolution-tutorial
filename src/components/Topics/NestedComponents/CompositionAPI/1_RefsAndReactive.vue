<template>
    <div>
        <h4>Ref Variables:</h4>
        <p>Firstname: {{ firstname }}</p>
        <p>Lastname: {{ lastname }}</p>
        <p>Heroname: {{ heroname }}</p>
        <p>Greet: {{ greet }}</p>
        <h4>Reactive Variable:</h4>
        <p>Name: {{ profile.name }}</p>
        <p>Email: {{ profile.email }}</p>
        <p>Phone: {{ profile.contact }}</p>
        <p>Company: {{ profile.company }}</p>
    </div>
</template>

<script>
/* eslint-disable */
import { ref, reactive } from 'vue'
export default {
    name: 'RefsAndReactive',
    setup() {
        const firstname = ref('Steve')
        const lastname = ref('Rogers')
        const heroname = ref('Captain America')
        const greet = `Hello ${firstname.value} ${lastname.value} a.k.a. ${heroname.value}`

        const profile = reactive({
            name: 'Anmol Singh',
            email: 'anmolsingh@gmail.com',
            contact: '9828378232',
            company: 'Eli Lilly',
        })

        return {
            firstname,
            lastname,
            heroname,
            greet,
            profile
        }
    }
}
</script>

<style scoped>

</style>