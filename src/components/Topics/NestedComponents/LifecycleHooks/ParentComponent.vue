<template>
    <div class="parent-component">
        <h3>This is Parent Component</h3>
        <button @click="showChild = !showChild">Toggle Child Component</button>
        <ChildComponent v-if="showChild"/>
    </div>
</template>

<script>
/* eslint-disable */
import ChildComponent from './ChildComponent.vue'
export default {
    name: 'ParentComponent',
    components: {
        ChildComponent,
    },
    data() {
        return {
            showChild: true,
        }
    },
    beforeCreate() {
        console.log("Parent Component breforeCreate()")
    },
    created() {
        console.log("Parent Component created()")
    },
    beforeMount() {
        console.log("Parent Component beforeMount()")
    },
    mounted() {
        console.log("Parent Component mounted()")
    },
    beforeUpdate() {
        console.log("Parent Component beforeUpdate()")
    },
    updated() {
        console.log("Parent Component updated()")
    },
    beforeUnmount() {
        console.log("Parent Component beforeUnmount()")
    },
    unmounted() {
        console.log("Parent Component unmounted()")
    },
}
</script>

<style scoped>
.parent-component {
    border: 1px solid #999;
    padding: 20px;
    width: 500px;
    margin-top: 20px;
}
.parent-component button {
    font-size: 14px;
    line-height: 1.3;
    padding: 6px 12px;
    margin-top: 10px;
    border: 1px solid #999;
}
</style>