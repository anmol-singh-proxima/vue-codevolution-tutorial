<template>
    <div>
        <h1>Event Handling</h1>
        <form>
            <input type="text" v-model="name" />
        </form><br/>
        <button type="button" @click="addName(name, $event), incrementCount($event)">Add Name</button>
        <p>Name Count: {{count}}</p>
        <p v-if="names.length !== 0">Names: 
            <span v-for="name in names" :key="name">{{name}}, </span>
        </p>
    </div>
</template>

<script>
export default {
    name: 'EventHandling',
    data() {
        return {
            names: [],
            name: "",
            count: 0,
        }
    },
    methods: {
        addName(name, event) {
            console.log("Name Event:", event)
            this.names.push(name)
            this.name = ""
        },
        incrementCount(event) {
            console.log("Increment Event:", event)
            this.count++;
        }
    }
}
</script>