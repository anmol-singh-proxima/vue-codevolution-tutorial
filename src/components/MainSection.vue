<template>
    <div class="home-main-section">
        <Binding v-if="currentMenuIndex === 0" />
        <ConditionalRendering v-if="currentMenuIndex === 1" />
        <ListRendering v-if="currentMenuIndex === 2" />
        <EventHandling v-if="currentMenuIndex === 3" />
        <FormHandling v-if="currentMenuIndex === 4" />
        <ComputedProperties v-if="currentMenuIndex === 5" />
        <Watchers v-if="currentMenuIndex === 6" />
        <ComponentAndProps v-if="currentMenuIndex === 7" />
        <ProvideAndInject v-if="currentMenuIndex === 8" />
        <CustomComponentEvent v-if="currentMenuIndex === 9" />
    </div>
</template>

<script>
/* eslint-disable */
import Binding from './Topics/1_Binding.vue'
import ConditionalRendering from './Topics/2_ConditionalRendering.vue'
import ListRendering from './Topics/3_ListRendering.vue';
import EventHandling from './Topics/4_EventHandling.vue';
import FormHandling from './Topics/5_FormHandling.vue';
import ComputedProperties from './Topics/6_ComputedProperties.vue'
import Watchers from './Topics/7_Watchers.vue';
import ComponentAndProps from './Topics/8_ComponentAndProps.vue';
import ProvideAndInject from './Topics/9_ProvideAndInject.vue';
import CustomComponentEvent from './Topics/10_CustomComponentEvent.vue'
export default {
    name: 'MainSection',  
    components: {
        Binding,
        ConditionalRendering,
        ListRendering,
        EventHandling,
        FormHandling,
        ComputedProperties,
        Watchers,
        ComponentAndProps,
        ProvideAndInject,
        CustomComponentEvent,
    }, 
    props: {
        menuItems: Array,
        currentMenuIndex: Number,
        setMenuIndex: Function,
    },
}
</script>

<style>
.home-main-section {
    padding: 0 10px;
    padding-bottom: 30px;
}
.home-main-section h2 {
    text-decoration: underline;
    padding: 10px;
    margin: 0;
}
</style>