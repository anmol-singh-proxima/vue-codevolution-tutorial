<template>
    <div class="parent-component">
        <h4>ParentComponent</h4>
        <div>
            <p>The data from these inputs will be passed as props to ChildComponent</p>
            <input type="text" placeholder="First Name" v-model="firstname" />
            <input type="text" placeholder="Last Name" v-model="lastname" />
            <p v-if="heroname"><i>Heroname sent from ChildComponent: {{ heroname }}</i></p>
        </div>
        <ChildComponent :firstname="firstname" :lastname="lastname" @callHero="getHeroname"/>
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
        const firstname = ref('Natasha')
        const lastname = ref('Romanoff')
        const heroname = ref('')
        function getHeroname(name) {
            heroname.value = name
        }
        return {
            firstname,
            lastname,
            heroname,
            getHeroname,
        }
    }
}
</script>

<style scoped>
.parent-component {
    border: 1px solid #999;
    padding: 20px;
}
input {
    display: block;
    font-size: 14px;
    line-height: 1.3;
    padding: 6px 12px;
    margin-bottom: 10px;
    border: 1px solid #999;
}
</style>