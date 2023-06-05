<template>
    <div class="child-component">
        <h3>This is Child Component</h3>
        <button @click="showGrandChild = !showGrandChild">Toggle Grand Child Component</button>
        <GrandChildComponent v-if="showGrandChild"/>
    </div>
</template>

<script>
/* eslint-disable */
import GrandChildComponent from './GrandChildComponent.vue';
export default {
    name: 'ChildComponent',
    components: {
        GrandChildComponent,
    },
    data() {
        return {
            showGrandChild: true,
        }
    },
    beforeCreate() {
        console.log("Child Component breforeCreate()")
    },
    created() {
        console.log("Child Component created()")
    },
    beforeMount() {
        console.log("Child Component beforeMount()")
    },
    mounted() {
        console.log("Child Component mounted()")
    },
    beforeUpdate() {
        console.log("Child Component beforeUpdate()")
    },
    updated() {
        console.log("Child Component updated()")
    },
    beforeUnmount() {
        console.log("Child Component beforeUnmount()")
    },
    unmounted() {
        console.log("Child Component unmounted()")
    },
}
</script>

<style scoped>
.child-component {
    border: 1px solid #999;
    padding: 20px;
    width: 100%;
    margin-top: 20px;
}
.child-component button {
    font-size: 14px;
    line-height: 1.3;
    padding: 6px 12px;
    margin-top: 10px;
    border: 1px solid #999;
}
</style>