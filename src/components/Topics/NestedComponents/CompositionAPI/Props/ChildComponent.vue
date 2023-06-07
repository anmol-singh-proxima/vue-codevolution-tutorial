<template>
    <div class="class-component">
        <h4>ChildComponent</h4>
        <p>The data from ParentComponent is as follows</p>
        <p>Name: {{ fullname }}</p>
        <p>Heroname: {{ heroname }}</p>
    </div>
</template>

<script>
/* eslint-disable */
import { ref, computed } from 'vue'
export default {
    name: 'ChildComponent',
    props: ['firstname', 'lastname', 'heroname'],
    setup(props) {
        const fullname = computed(() => {
            return `${props.firstname} ${props.lastname}`
        })
        const heroname =  computed(() => {
            return `${props.heroname}`
        })
        return {
            fullname,
            heroname,
        }
    }
}
</script>

<style scoped>
.class-component {
    border: 1px solid #999;
    padding: 10px;
    margin-top: 10px;
}
</style>