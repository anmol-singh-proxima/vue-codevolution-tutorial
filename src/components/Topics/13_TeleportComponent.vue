<template>
    <div>
        <h2>Teleport Component</h2><hr/>
        <div class="teleport-component">
            <h3>Vue Teleport Component</h3>
            <p>
                This is an example of how you might use Vue Teleport. I think it is a pretty neat API that is yet another awesome escape hatch that Vue provides for practical reasons. Sometimes you just need to render something completely outside the Vue component tree.
            </p>
            <button @click="showModal = true">Show Modal</button>
            <teleport to="#modal-root">
                <Modal v-show="showModal" @close="showModal = false">
                    <p><b>This is the Modal message!</b></p><hr/>
                    <p>This is the Modal Component, and this is rendering completely outside the Vue component tree which comes under '#app' node in html. This comes under '#modal-root' node.</p>
                </Modal>
            </teleport>
        </div>
    </div>
</template>

<script>
/* eslint-disable */
import Modal from './NestedComponents/Modal.vue';
export default {
    name: 'TeleportComponent',
    components: {
    Modal,
    },
    data() {
        return {
        showModal: false,
        };
    },
}
</script>

<style scoped>
.teleport-component {
    width: 400px;
    box-shadow: 0 4px 8px 0 rgba(150, 160, 170, 0.5);
    padding: 20px;
}
.teleport-component button {
    font-size: 14px;
    padding: 6px 12px;
    line-height: 1.3;
}
</style>