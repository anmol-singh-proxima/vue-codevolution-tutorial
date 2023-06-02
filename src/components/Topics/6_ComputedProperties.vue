<template>
    <div>
        <h2>Computed Properties</h2>
        <hr/>
        <div class="computed-properties">
            <!-- Displaying Computed Property -->
            <div class="items">
                <h3>Items Table</h3>
                <table>
                    <tr><th>ID</th><th>Name</th><th>Price</th></tr>
                    <tr v-for="item in items" :key="item.id">
                        <td>{{item.id}}</td>
                        <td>{{item.name}}</td>
                        <td>{{item.price}}</td>
                    </tr>
                    <tr>
                        <th colspan="2">Total Price</th>
                        <th>{{itemTotalPrice}}</th>
                    </tr>
                </table>
            </div>
            <!-- Computed property with condition -->
            <div class="expensive-items">
                <h3>Expensive Items* Table</h3>
                <table>
                    <tr><th>ID</th><th>Name</th><th>Price</th></tr>
                    <tr v-for="item in expensiveItems" :key="item.id">
                        <td>{{item.id}}</td>
                        <td>{{item.name}}</td>
                        <td>{{item.price}}</td>
                    </tr>
                </table>
                <span>*Items whose price >= 500</span>
            </div>
            <!-- Adding Items dynamically -->
            <div class="add-items">
                <h3>Add more items to the Table</h3>
                <form class="items-form" @submit.prevent="addItem">
                    <label>Enter item name:</label>
                    <input type="text" v-model="name" />
                    <label>Enter item price:</label>
                    <input type="number" v-model="price" />
                    <button type="submit">Add item</button>
                </form>
            </div>
            <!-- Computed Setter -->
            <div class="profile">
                <h3>Profile</h3>
                <p>Firstname: {{firstname}}</p>
                <p>Lastname: {{lastname}}</p>
                <p>Fullname: {{fullname}}</p>
                <button @click="changeFullname">Change Fullname</button>
            </div>
        </div>
    </div>
</template>

<script>
/* eslint-disable */
export default {
    name: 'ComputedProperties',
    data() {
        return {
            items: [
                { id: '1', name: 'Notebook', price: 50 },
                { id: '2', name: 'Bottle', price: 800 },
                { id: '3', name: 'Specs', price: 2800 },
                { id: '4', name: 'Charger', price: 450 },
            ],
            id: '',
            name: '',
            price: null,
            firstname: 'Anmol',
            lastname: 'Singh'
        }
    },
    computed: {
        itemTotalPrice() {
            console.log("itemTotal")
            return this.items.reduce((total, item) => (total = total + item.price), 0)
        },
        expensiveItems() {
            console.log("expensive items")
            return this.items.filter(item => item.price >= 500)
        },
        fullname: {
            get() {
                return `${this.firstname} ${this.lastname}`
            },
            set(name) {
                const names = name.split(' ')
                this.firstname = names[0]
                this.lastname = names[1]
            }
        }
    },
    methods: {
        addItem() {
            this.id = this.items.length + 1
            this.items.push({
                id: this.id,
                name: this.name,
                price: this.price,
            })
            this.id = '',
            this.name = '',
            this.price = null
        },
        changeFullname() {
            this.fullname = 'Bhagat Singh'
        }
    }
}
</script>

<style scoped>
.computed-properties {
    display: flex;
    flex-wrap: wrap;
    flex-direction: row;
}
.items, .expensive-items, .add-items, .profile {
    width: 33%;
    padding-right: 10px;
}
.items table, .expensive-items table {
    border-collapse: collapse;
    margin-bottom: 10px;
}
.items table th, .items table td, .expensive-items table th, .expensive-items table td {
    border: 1px solid #333;
    padding: 6px 12px;
}
.expensive-items span {
    font-size: 13px;
    font-style: italic;
}
.items-form input, .items-form label {
    display: block;
}
.items-form input {
    font-size: 14px;
    padding: 6px 12px;
    margin-bottom: 15px;
    border: 1px solid #888;
}
.items-form label {
    font-size: 13px;
    margin-bottom: 10px;
}
.items-form button {
    font-size: 15px;
    padding: 8px 16px;
    color: #fff;
    background-color: chocolate;
    border: 1px solid chocolate;
}
</style>