<template>
    <div class="grandchild-component">
        <h3>This is Grand Child Component</h3>
    </div>
</template>

<script>
/* eslint-disable */
export default {
    name: 'GrandChildComponent',
    beforeCreate() {
        console.log("Grand Child Component breforeCreate()")
    },
    created() {
        console.log("Grand Child Component created()")
    },
    beforeMount() {
        console.log("Grand Child Component beforeMount()")
    },
    mounted() {
        console.log("Grand Child Component mounted()")
    },
    beforeUpdate() {
        console.log("Grand Child Component beforeUpdate()")
    },
    updated() {
        console.log("Grand Child Component updated()")
    },
    beforeUnmount() {
        console.log("Grand Child Component beforeUnmount()")
    },
    unmounted() {
        console.log("Grand Child Component unmounted()")
    },
}
</script>

<style scoped>
.grandchild-component {
    border: 1px solid #999;
    padding: 20px;
    width: 100%;
    margin-top: 20px;
}
</style>