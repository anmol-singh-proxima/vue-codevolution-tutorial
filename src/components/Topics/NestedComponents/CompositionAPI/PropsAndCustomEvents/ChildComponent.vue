<template>
    <div class="child-component">
        <h4>ChildComponent</h4>
        <p>Name sent from ParentComponent: {{ fullname }}</p>
        <p>Enter Superhero Name for the given name</p>
        <input type="text" placeholder="Hero Name" v-model="heroname" />
        <button @click="sendHeroname">Send Heroname</button>
    </div>
</template>

<script>
/* eslint-disable */
import { ref, computed } from 'vue'
export default {
    name: 'ChildComponent',
    props: ['firstname', 'lastname', 'heroname'],
    emits: ['callHero'],
    setup(props, context) {
        const fullname = computed(() => {
            return `${props.firstname} ${props.lastname}`
        })
        const heroname = ref('')
        function sendHeroname() {
            context.emit('callHero', heroname.value)
        }
        return {
            fullname,
            heroname,
            sendHeroname,
        }
    }
}
</script>

<style scoped>
.child-component {
    border: 1px solid #999;
    padding: 10px;
    margin-top: 10px;
}
.child-component h4, .child-component p {
    padding: 6px;
    margin: 0;
}
input, button {
    display: block;
    font-size: 14px;
    line-height: 1.3;
    padding: 6px 12px;
    margin-bottom: 10px;
    border: 1px solid #999;
}
</style>