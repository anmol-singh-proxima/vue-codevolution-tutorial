<template>
    <div>
        <h1>List Rendering</h1>
        <h2>Normal List Rendering</h2>
        <h3>Names:</h3>
        <div v-for="(name, index) in names" :key="name">
            <p>{{index}} - {{name}}</p>
        </div>
        <h3>Full Names:</h3>
        <div v-for="name in fullNames" :key="name.first">
            <p>{{name.first}} {{name.last}}</p>
        </div>
        <h3>My Info:</h3>
        <p v-for="(value, key, index) in myInfo" :key="value">{{index}} - {{key}}: {{value}}</p>
        <h3>All Actors Details:</h3>
        <table border="1">
            <tr>
                <th>S.No.</th>
                <th>Name</th>
                <th>Movies</th>
                <th>Oscar</th>
            </tr>
            <tr v-for="(actor, index) in actors" :key="actor.name">
                <td>{{index}}</td>
                <td>{{actor.name}}</td>
                <td>
                    <p v-for="movie in actor.movies" :key="movie">{{movie}}</p>
                </td>
                <td>{{actor.oscar ? 'Yes' : 'No'}}</td>
            </tr>
        </table>
        <h2>Conditional List Rendering</h2>
        <h3>Actors with Oscar</h3>
        <table border="1">
            <tr>
                <th>S.No.</th>
                <th>Name</th>
                <th>Movies</th>
                <th>Oscar</th>
            </tr>
            <template v-for="(actor, index) in actors" :key="actor.name">
                <tr v-if="actor.oscar">
                    <td>{{index}}</td>
                    <td>{{actor.name}}</td>
                    <td><p v-for="movie in actor.movies" :key="movie">{{movie}}</p></td>
                    <td>{{actor.oscar ? 'Yes' : 'No'}}</td>
                </tr>
            </template>
        </table>
    </div>
</template>

<script>
export default {
    name: 'ListRendering',
    data() {
        return {
            names: ['Bruce', 'Clarke', 'Diana'],
            fullNames: [
                { 
                    first: 'Bruce',
                    last: 'Wayne'
                },
                { 
                    first: 'Clarke',
                    last: 'Kent'
                },
                { 
                    first: 'Princess',
                    last: 'Diana'
                }
            ],
            actors: [
                {
                    name: 'Christian Bale',
                    movies: ['The Batman', 'The Prestige'],
                    oscar: false,
                },
                {
                    name: 'Leonardo De Caprio',
                    movies: ['Inception', 'Titanic'],
                    oscar: true
                },
                {
                    name: 'Marlon Brando',
                    movies: ['The Godfather 1', 'The Godfather 2'],
                    oscar: false
                },
                {
                    
                    name: 'Al Pacino',
                    movies: ['The Godfather 1', 'The Godfather 2'],
                    oscar: true
                }
            ],
            myInfo: {
                name: 'Anmol Singh',
                company: 'Eli Lilly',
                designation: 'Analyst - Software Configuration and Development',
                hometown: 'Aligarh, Uttar Pradesh'
            }
        }
    }
}
</script>