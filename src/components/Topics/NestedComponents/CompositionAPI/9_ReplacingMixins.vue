<template>
    <div>
        <p>Here, we have two counters and both the counters use the same functionality called 'useCounter' as to replace mixins in Composition API</p>
        <ClickCounter />
        <HoverCounter />
    </div>
</template>

<script>
/* eslint-disable */
import ClickCounter from './ReplacingMixins/ClickCounter.vue';
import HoverCounter from './ReplacingMixins/HoverCounter.vue';
export default {
    name: 'ReplacingMixins',
    components: {
        ClickCounter,
        HoverCounter,
    }
}
</script>

<style scoped>

</style>