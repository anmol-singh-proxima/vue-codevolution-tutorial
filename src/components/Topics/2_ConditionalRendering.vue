<template>
    <div>
        <h2>Conditional Rendering</h2>
        <hr/>
        <p v-if="num === 0">Number is zero</p>
        <p v-else-if="num>0">Number is positive</p>
        <p v-else-if="num<0">Number is negative</p>
        <p v-else>Not a number</p>
        <template v-if="display">
            <h3>Profile:</h3>
            <p>Anmol Singh</p>
            <p>Lives in Bangalore</p>
            <p>Study Full Stack</p>
        </template>
        <h3>Cities in India:</h3>
        <div v-show="showDiv">
            <p>Delhi</p>
            <p>Aligarh</p>    
            <p>Bangalore</p>
            <p>Hyderabad</p>
            <p>Meerut</p>
        </div>
        <button type="button" @click="toggleCities">{{buttonText}}</button>
    </div>
</template>


<script>
/* eslint-disable */
export default {
    name: 'ConditionalRendering',
    data() {
        return {
            num: 0,
            display: false,
            showDiv: true,
            buttonText: 'Hide Cities'
        }
    },
    methods: {
        toggleCities() {
            this.showDiv = !this.showDiv
            this.buttonText = this.showDiv ? 'Hide Cities' : 'Show Cities'
        }
    }
}
</script>

<style scoped>
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