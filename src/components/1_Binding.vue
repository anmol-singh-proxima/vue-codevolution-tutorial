<template>
    <div>
        <h1>Binding</h1>
        <div v-html="content"></div>
        <a v-bind:class="linkClass" href="">The link is {{linkStatus}}</a><br/>
        <button type="button" @click="toggleActive">Click to make the link {{buttonText}}</button>
    </div>
</template>

<script>
export default {
    name: 'Binding',
    data() {
        return {
            name: 'Anmol',
            content: '',
            isActive: true,
            linkClass: 'active',
            linkStatus: 'Active',
            buttonText: 'Inactive',
        }
    },
    mounted() {
        this.content = `Hello <b>${this.name}</b>`
    },
    methods: {
        toggleActive() {
            if(this.isActive) {
                this.isActive = false
                this.linkClass = 'inactive',
                this.linkStatus = 'Inactive'
                this.buttonText = 'Active'
            } else {
                this.isActive = true
                this.linkClass = 'active',
                this.linkStatus = 'Active'
                this.buttonText = 'Inactive'
            }
        }
    }
}
</script>

<style>
.active {
    color: red;
    text-decoration: underline;
    cursor: pointer;
}
.inactive {
    color: blue;
    text-decoration: none;
    cursor: none;
}
</style>