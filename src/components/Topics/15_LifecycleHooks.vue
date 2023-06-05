<template>
    <div>
        <h2>Lifecycle Hooks</h2><hr/>
        <div>
            <p>This is the basic experiment for the Lifecycle-Hooks</p>
            <p>The ParentComponent contains the ChildComponent and a button to toggle the ChildComponent.</p>
            <p>Similarly, the ChildComponent contains the GrandChildComponent and a button to toggle the GrandChildComponent.</p>
            <p>The entire Lifecycle-Hooks series can be seen in Console Log</p>
            <ParentComponent />
        </div>
    </div>
</template>

<script>
/* eslint-disable */
import ParentComponent from './NestedComponents/LifecycleHooks/ParentComponent.vue';
export default {
    name: 'LifecycleHooks',
    components: {
        ParentComponent,
    }
}
</script>

<style scoped>

</style>