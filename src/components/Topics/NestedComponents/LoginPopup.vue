<template>
    <div class="popup">
        <h3>Login Popup</h3>
        <form @submit.prevent="submitForm">
            <InputText v-model="user.username" :placeholder="'Username'" />
            <InputPassword v-model="user.password" :placeholder="'Password'" />
            <button type="Submit">Login</button>
        </form>
    </div>
</template>

<script>
/* eslint-disable */
import InputText from './CustomFormFields/InputText.vue'
import InputPassword from './CustomFormFields/InputPassword.vue'
export default {
    name: 'LoginPopup',
    components: {
        InputText,
        InputPassword
    },
    emits: {
        login: (user) => {
            if(user.username && user.password) {
                return true
            } else {
                return false
            }
        }
    },
    data() {
        return {
            user: {
                username: '',
                password: '',
            }
        }
    },
    methods: {
        submitForm() {
            this.$emit('login', this.user)
        }
    }
}
</script>

<style scoped>
.popup {
    border: 1px solid #888;
    width: fit-content;
    padding: 10px;
    margin-top: 10px;
    text-align: center;
    margin: auto;
}
.popup input {
    display: block;
    font-size: 14px;
    padding: 6px 12px;
    margin-bottom: 15px;
    width: 250px;
    border: 1px solid #888;
}
.popup button {
    padding: 6px 12px;
    font-size: 14px;
    border: 1px solid #888;
}
</style>