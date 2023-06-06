<template>
    <div>
        <h2>Mixins</h2><hr/>
        <div>
            <p>Here are two Components showing the Counter Increment functionality by using mixins</p>
            <ClickCounter />
            <HoverCounter />
        </div>
    </div>
</template>

<script>
/* eslint-disable */
import ClickCounter from './NestedComponents/Mixins/ClickCounter.vue';
import HoverCounter from './NestedComponents/Mixins/HoverCounter.vue';
export default {
    name: 'Mixins',
    components: {
        ClickCounter,
        HoverCounter,
    }
}
</script>

<style scoped>

</style>