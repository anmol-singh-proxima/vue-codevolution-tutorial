<template>
    <div>
        <p>Here is one ParentComponent and a ChildComponent, ParentComponent will pass the props to ChildComponent and ChildComponent will display it. This all will be done using Composition API.</p>
        <ParentComponent />
    </div>
</template>

<script>
/* eslint-disable */
import ParentComponent from './Props/ParentComponent.vue';
export default {
    name: 'Props',
    components: {
        ParentComponent,
    }
}
</script>

<style scoped>

</style>