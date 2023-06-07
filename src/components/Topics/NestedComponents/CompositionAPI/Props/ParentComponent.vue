<template>
    <div class="parent-component">
        <h4>ParentComponent</h4>
        <div>
            <p>The data from these inputs will be passed as props to ChildComponent</p>
            <input type="text" placeholder="First Name" v-model="firstname" />
            <input type="text" placeholder="Last Name" v-model="lastname" />
            <input type="text" placeholder="Hero Name" v-model="heroname" />
        </div>
        <ChildComponent :firstname="firstname" :lastname="lastname" :heroname="heroname" />
    </div>
</template>

<script>
/* eslint-disable */
import { ref, reactive, toRefs } from 'vue'
import ChildComponent from './ChildComponent.vue';
export default {
    name: 'ParentComponent',
    components: {
        ChildComponent,
    },
    setup() {
        const firstname = ref('Anmol')
        const lastname = ref('Singh')
        const heroname = ref('Shera')
        return {
            firstname,
            lastname,
            heroname
        }
    }
}
</script>

<style scoped>
.parent-component {
    border: 1px solid #999;
    padding: 10px;
}
.parent-component h4, .parent-component p {
    padding: 6px;
    margin: 0;
}
</style>