<template>
    <div>
        <h2>Custom Component Event</h2><hr/>
        <div class="custom-event">
            <p>Click the button to enter Login Info</p>
            <button @click="showLoginPopup">Show Login Popup</button>
            <LoginPopup v-show="showPopup" @login="closeLoginPopup" />
            <div v-show="showLoginInfo">
                <h4>Login Info</h4>
                <p>Username: {{ user.username }}</p>
                <p>Password: {{ user.password }}</p>
            </div>
        </div>
    </div>
</template>

<script>
/* eslint-disable */
import LoginPopup from './NestedComponents/LoginPopup.vue';
export default {
    name: 'CustomComponentEvent',
    components: {
        LoginPopup,
    },
    data() {
        return {
            showPopup: false,
            showLoginInfo: false,
            user: {},
        }
    },
    methods: {
        closeLoginPopup(user) {
            this.showPopup = false
            this.showLoginInfo = true
            this.user = user
        },
        showLoginPopup() {
            this.showPopup = true
            this.showLoginInfo = false
        }
    }
}
</script>

<style scoped>
.custom-event button {
    padding: 6px 12px;
    font-size: 14px;
    border: 1px solid #888;
}
</style>