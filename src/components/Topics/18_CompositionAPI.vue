<template>
    <div>
        <h2>Composition API</h2><hr/>
        <div>
            <div>
                <h3>1. Refs And Reactive</h3>
                <RefsAndReactive />
            </div><hr/>
            <div>
                <h3>2. ToRefs</h3>
                <ToRefs />
            </div><hr/>
            <div>
                <h3>3. Replace Methods</h3>
                <ReplaceMethods />
            </div><hr/>
            <div>
                <h3>4. Replace Computed</h3>
                <ReplaceComputed />
            </div><hr/>
            <div>
                <h3>5. Replace Watchers</h3>
                <ReplaceWatchers />
            </div><hr/>
            <div>
                <h3>5. Provide and Inject</h3>
                <ProvideInject />
            </div><hr/>
            <div>
                <h3>6. Template Ref</h3>
                <TemplateRef />
            </div><hr/>
            <div>
                <h3>7. Props and Custom Events</h3>
                <PropsAndCustomEvents />
            </div><hr/>
            <div>
                <h3>8. Replacing Mixins</h3>
                <ReplacingMixins />
            </div><hr/>
        </div>
    </div>
</template>

<script>
/* eslint-disable */
import RefsAndReactive from './NestedComponents/CompositionAPI/1_RefsAndReactive.vue'
import ToRefs from './NestedComponents/CompositionAPI/2_ToRefs.vue'
import ReplaceMethods from './NestedComponents/CompositionAPI/3_ReplaceMethods.vue';
import ReplaceComputed from './NestedComponents/CompositionAPI/4_ReplaceComputed.vue';
import ReplaceWatchers from './NestedComponents/CompositionAPI/5_ReplaceWatchers.vue';
import ProvideInject from './NestedComponents/CompositionAPI/6_ProvideInject.vue';
import TemplateRef from './NestedComponents/CompositionAPI/7_TemplateRef.vue';
import PropsAndCustomEvents from './NestedComponents/CompositionAPI/8_PropsAndCustomEvents.vue';
import ReplacingMixins from './NestedComponents/CompositionAPI/9_ReplacingMixins.vue';
export default {
    name: 'CompositionAPI',
    components: {
        RefsAndReactive,
        ToRefs,
        ReplaceMethods,
        ReplaceComputed,
        ReplaceWatchers,
        ProvideInject,
        TemplateRef,
        PropsAndCustomEvents,
        ReplacingMixins,
    }
}
</script>

<style scoped>

</style>